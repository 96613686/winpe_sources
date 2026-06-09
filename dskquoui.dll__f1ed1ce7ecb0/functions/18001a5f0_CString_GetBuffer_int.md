# CString::GetBuffer(int)

- ea: `0x18001a5f0`
- end: `0x18001a6c1`
- name: `?GetBuffer@CString@@QEAAPEAGH@Z`
- size: `209`
- prototype: `unsigned __int16 *(CString *__hidden this, int)`
- caller_count: `13`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000a07c`
- `0x18000b090`
- `0x18000e4fc`
- `0x18000fc54`
- `0x1800126c0`
- `0x180013d44`
- `0x180014ca8`
- `0x18001510c`
- `0x1800151c0`
- `0x180016470`
- `0x180018384`
- `0x18001bf58`
- `0x18001bfc8`

## callees

- `0x180001534`
- `0x180005410`
- `0x180006ec0`
- `0x180019e38`
- `0x18001a15c`
- `0x18001a5f0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a678`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a678`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int16 *__fastcall CString::GetBuffer(const unsigned __int16 ***this, int a2)
{
  int v2; // esi
  unsigned __int16 ***v3; // rbx
  CString::StringValue *v4; // rax
  __int64 v5; // rdi
  unsigned __int16 **v6; // rsi
  _WORD *v7; // rdx

  v2 = a2;
  v3 = (unsigned __int16 ***)(this + 1);
  if ( a2 == -1 )
    v2 = *((_DWORD *)*v3 + 2);
  CString::CopyOnWrite(this);
  if ( v2 > *((_DWORD *)*v3 + 2) )
  {
    v4 = (CString::StringValue *)operator new(0x18u);
    if ( v4 )
      v5 = CString::StringValue::StringValue(v4, v2);
    else
      v5 = 0;
    StringCchCopyW(*(unsigned __int16 **)v5, v2, **v3);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)*v3 + 3, 0xFFFFFFFF) == 1 )
    {
      v6 = *v3;
      if ( *v3 )
      {
        if ( *v6 )
          LocalFree(*v6);
        operator delete(v6);
      }
    }
    *v3 = (unsigned __int16 **)v5;
    v7 = (_WORD *)(*(_QWORD *)v5 + 2 * (*(int *)(v5 + 8) - 1LL));
    if ( (unsigned __int64)v7 >= *(_QWORD *)v5 && *v7 )
      *v7 = 0;
  }
  return **v3;
}

```

## disassembly

```asm
0x18001a5f0  mov     [rsp+arg_8], rbx
0x18001a5f5  mov     [rsp+arg_10], rsi
0x18001a5fa  push    rdi
0x18001a5fb  sub     rsp, 20h
0x18001a5ff  mov     esi, edx
0x18001a601  lea     rbx, [rcx+8]
0x18001a605  cmp     edx, 0FFFFFFFFh
0x18001a608  jnz     short loc_18001A610
0x18001a60a  mov     rax, [rbx]
0x18001a60d  mov     esi, [rax+8]
0x18001a610  call    ?CopyOnWrite@CString@@AEAAXXZ; CString::CopyOnWrite(void)
0x18001a615  mov     rax, [rbx]
0x18001a618  cmp     esi, [rax+8]
0x18001a61b  jle     loc_18001A6AB
0x18001a621  mov     ecx, 18h; uBytes
0x18001a626  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a62b  mov     [rsp+28h+arg_0], rax
0x18001a630  test    rax, rax
0x18001a633  jz      short loc_18001A644
0x18001a635  mov     edx, esi; int
0x18001a637  mov     rcx, rax; this
0x18001a63a  call    ??0StringValue@CString@@QEAA@H@Z; CString::StringValue::StringValue(int)
0x18001a63f  mov     rdi, rax
0x18001a642  jmp     short loc_18001A646
0x18001a644  xor     edi, edi
0x18001a646  mov     r8, [rbx]
0x18001a649  movsxd  rdx, esi; unsigned __int64
0x18001a64c  mov     r8, [r8]; unsigned __int16 *
0x18001a64f  mov     rcx, [rdi]; unsigned __int16 *
0x18001a652  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a657  mov     r11, [rbx]
0x18001a65a  or      eax, 0FFFFFFFFh
0x18001a65d  lock xadd [r11+0Ch], eax
0x18001a663  cmp     eax, 1
0x18001a666  jnz     short loc_18001A68B
0x18001a668  mov     rsi, [rbx]
0x18001a66b  test    rsi, rsi
0x18001a66e  jz      short loc_18001A68B
0x18001a670  mov     rcx, [rsi]; hMem
0x18001a673  test    rcx, rcx
0x18001a676  jz      short loc_18001A67E
0x18001a678  call    cs:__imp_LocalFree
0x18001a67e  mov     edx, 18h; unsigned __int64
0x18001a683  mov     rcx, rsi; void *
0x18001a686  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a68b  mov     [rbx], rdi
0x18001a68e  mov     rcx, [rdi]
0x18001a691  movsxd  rdx, dword ptr [rdi+8]
0x18001a695  dec     rdx
0x18001a698  lea     rdx, [rcx+rdx*2]
0x18001a69c  cmp     rdx, rcx
0x18001a69f  jb      short loc_18001A6AB
0x18001a6a1  xor     eax, eax
0x18001a6a3  cmp     ax, [rdx]
0x18001a6a6  jz      short loc_18001A6AB
0x18001a6a8  mov     [rdx], ax
0x18001a6ab  mov     rax, [rbx]
0x18001a6ae  mov     rax, [rax]
0x18001a6b1  mov     rbx, [rsp+28h+arg_8]
0x18001a6b6  mov     rsi, [rsp+28h+arg_10]
0x18001a6bb  add     rsp, 20h
0x18001a6bf  pop     rdi
0x18001a6c0  retn
```
