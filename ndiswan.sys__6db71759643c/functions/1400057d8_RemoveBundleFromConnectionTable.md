# RemoveBundleFromConnectionTable

- ea: `0x1400057d8`
- end: `0x140005878`
- name: `RemoveBundleFromConnectionTable`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140005494`

## callees

- `0x1400057d8`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x140005859`
- `NDIS!NdisReleaseRWLock` at `0x140005859`
- `NDIS!NdisAcquireRWLockWrite` at `0x140005802`
- `NDIS!NdisAcquireRWLockWrite` at `0x140005802`

## pseudocode

```c
void __fastcall RemoveBundleFromConnectionTable(__int64 *a1)
{
  __int64 v1; // rdi
  _DWORD *v3; // rax
  __int64 v4; // r9
  __int64 *v5; // rcx
  __int64 **v6; // rdx
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((unsigned int *)a1 + 8);
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockWrite(ConnTableLock, &LockState, 0);
  if ( (_DWORD)v1 )
  {
    v3 = ConnectionTable;
    if ( (unsigned int)v1 <= *((_DWORD *)ConnectionTable + 1) )
    {
      v4 = *((_QWORD *)ConnectionTable + 8);
      if ( *(_QWORD *)(v4 + 8 * v1) )
      {
        v5 = (__int64 *)*a1;
        if ( *(__int64 **)(*a1 + 8) != a1 || (v6 = (__int64 **)a1[1], *v6 != a1) )
          __fastfail(3u);
        *v6 = v5;
        v5[1] = (__int64)v6;
        *(_QWORD *)(v4 + 8 * v1) = 0;
        --v3[4];
      }
    }
  }
  NdisReleaseRWLock(ConnTableLock, &LockState);
}

```

## disassembly

```asm
0x1400057d8  mov     [rsp+arg_8], rbx
0x1400057dd  push    rdi
0x1400057de  sub     rsp, 20h
0x1400057e2  mov     edi, [rcx+20h]
0x1400057e5  lea     rdx, [rsp+28h+LockState]; LockState
0x1400057ea  xor     eax, eax
0x1400057ec  mov     rbx, rcx
0x1400057ef  mov     rcx, cs:ConnTableLock; Lock
0x1400057f6  xor     r8d, r8d; Flags
0x1400057f9  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x1400057fe  mov     [rsp+28h+LockState.Flags], al
0x140005802  call    cs:__imp_NdisAcquireRWLockWrite
0x140005809  nop     dword ptr [rax+rax+00h]
0x14000580e  test    edi, edi
0x140005810  jz      short loc_14000584D
0x140005812  mov     rax, cs:ConnectionTable
0x140005819  cmp     edi, [rax+4]
0x14000581c  ja      short loc_14000584D
0x14000581e  mov     r9, [rax+40h]
0x140005822  cmp     qword ptr [r9+rdi*8], 0
0x140005827  jz      short loc_14000584D
0x140005829  mov     rcx, [rbx]
0x14000582c  cmp     [rcx+8], rbx
0x140005830  jnz     short loc_140005871
0x140005832  mov     rdx, [rbx+8]
0x140005836  cmp     [rdx], rbx
0x140005839  jnz     short loc_140005871
0x14000583b  mov     [rdx], rcx
0x14000583e  mov     [rcx+8], rdx
0x140005842  mov     qword ptr [r9+rdi*8], 0
0x14000584a  dec     dword ptr [rax+10h]
0x14000584d  mov     rcx, cs:ConnTableLock; Lock
0x140005854  lea     rdx, [rsp+28h+LockState]; LockState
0x140005859  call    cs:__imp_NdisReleaseRWLock
0x140005860  nop     dword ptr [rax+rax+00h]
0x140005865  mov     rbx, [rsp+28h+arg_8]
0x14000586a  add     rsp, 20h
0x14000586e  pop     rdi
0x14000586f  retn
0x140005871  mov     ecx, 3
0x140005876  int     29h; Win8: RtlFailFast(ecx)
```
