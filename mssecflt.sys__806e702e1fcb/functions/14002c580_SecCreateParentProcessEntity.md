# SecCreateParentProcessEntity

- ea: `0x14002c580`
- end: `0x14002c6ae`
- name: `SecCreateParentProcessEntity`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14002c6b0`

## callees

- `0x1400067a4`
- `0x140006b6c`
- `0x14000add8`
- `0x140011650`
- `0x14002c580`
- `0x14002d400`

## import_xrefs

- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002c5d8`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002c5d8`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002c5f5`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002c60b`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002c5f5`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002c60b`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c684`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c684`

## pseudocode

```c
int __fastcall SecCreateParentProcessEntity(void *a1, LONGLONG a2, char a3, __int64 a4)
{
  LONGLONG v7; // rax
  LONGLONG TimeQuadPart; // rax
  struct _KPROCESS *v9; // rcx
  struct _SLIST_ENTRY *v10; // rcx
  int Next; // eax
  PSLIST_ENTRY ListEntry; // [rsp+20h] [rbp-28h] BYREF
  PEPROCESS Process; // [rsp+28h] [rbp-20h] BYREF

  Process = 0;
  *(_OWORD *)a4 = 0;
  *(_OWORD *)(a4 + 16) = 0;
  *(_OWORD *)(a4 + 32) = 0;
  *(_DWORD *)(a4 + 40) = -1;
  *(_QWORD *)a4 = a1;
  ListEntry = 0;
  LODWORD(v7) = PsLookupProcessByProcessId(a1, &Process);
  if ( (int)v7 >= 0 )
  {
    if ( a3 || (v7 = PsGetProcessCreateTimeQuadPart(Process), v7 < a2) )
    {
      TimeQuadPart = PsGetProcessCreateTimeQuadPart(Process);
      v9 = Process;
      *(_QWORD *)(a4 + 8) = TimeQuadPart;
      SecGetProcessStartKey(v9);
      SecGetParentProcessName(*(HANDLE *)a4);
      LODWORD(v7) = SecGetProcessContextByStartkey(*(_QWORD *)(a4 + 16), &ListEntry);
      if ( (int)v7 >= 0 )
      {
        v10 = ListEntry;
        if ( *((_DWORD *)&ListEntry[23].Next + 3) )
          Next = (int)ListEntry[21].Next;
        else
          Next = *((_DWORD *)&ListEntry[16].Next + 2);
        *(_DWORD *)(a4 + 40) = Next;
        LODWORD(v7) = SecReleaseProcessContext(v10);
      }
      else
      {
        *(_DWORD *)(a4 + 40) = -1;
      }
    }
  }
  if ( Process )
    LODWORD(v7) = ObfDereferenceObject(Process);
  return v7;
}

```

## disassembly

```asm
0x14002c580  mov     r11, rsp
0x14002c583  mov     [r11+10h], rbx
0x14002c587  mov     [r11+18h], rsi
0x14002c58b  push    rdi
0x14002c58c  sub     rsp, 40h
0x14002c590  mov     rax, cs:__security_cookie
0x14002c597  xor     rax, rsp
0x14002c59a  mov     [rsp+48h+var_18], rax
0x14002c59f  xorps   xmm0, xmm0
0x14002c5a2  mov     qword ptr [r11-20h], 0
0x14002c5aa  movups  xmmword ptr [r9], xmm0
0x14002c5ae  mov     rsi, rdx
0x14002c5b1  lea     rdx, [r11-20h]; Process
0x14002c5b5  movups  xmmword ptr [r9+10h], xmm0
0x14002c5ba  mov     rdi, r9
0x14002c5bd  mov     bl, r8b
0x14002c5c0  movups  xmmword ptr [r9+20h], xmm0
0x14002c5c5  mov     dword ptr [r9+28h], 0FFFFFFFFh
0x14002c5cd  mov     [r9], rcx
0x14002c5d0  mov     qword ptr [r11-28h], 0
0x14002c5d8  call    cs:__imp_PsLookupProcessByProcessId
0x14002c5df  nop     dword ptr [rax+rax+00h]
0x14002c5e4  test    eax, eax
0x14002c5e6  js      loc_14002C67A
0x14002c5ec  test    bl, bl
0x14002c5ee  jnz     short loc_14002C606
0x14002c5f0  mov     rcx, [rsp+48h+Process]; Process
0x14002c5f5  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14002c5fc  nop     dword ptr [rax+rax+00h]
0x14002c601  cmp     rax, rsi
0x14002c604  jge     short loc_14002C67A
0x14002c606  mov     rcx, [rsp+48h+Process]; Process
0x14002c60b  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14002c612  nop     dword ptr [rax+rax+00h]
0x14002c617  mov     rcx, [rsp+48h+Process]; Process
0x14002c61c  lea     rbx, [rdi+10h]
0x14002c620  mov     rdx, rbx
0x14002c623  mov     [rdi+8], rax
0x14002c627  call    SecGetProcessStartKey
0x14002c62c  mov     rdx, [rbx]
0x14002c62f  lea     r8, [rdi+18h]
0x14002c633  mov     rcx, [rdi]; ProcessId
0x14002c636  call    SecGetParentProcessName
0x14002c63b  mov     rcx, [rbx]
0x14002c63e  lea     rdx, [rsp+48h+ListEntry]
0x14002c643  call    SecGetProcessContextByStartkey
0x14002c648  test    eax, eax
0x14002c64a  jns     short loc_14002C655
0x14002c64c  mov     dword ptr [rdi+28h], 0FFFFFFFFh
0x14002c653  jmp     short loc_14002C67A
0x14002c655  mov     rcx, [rsp+48h+ListEntry]; ListEntry
0x14002c65a  mov     eax, [rcx+17Ch]
0x14002c660  test    eax, eax
0x14002c662  jz      short loc_14002C66C
0x14002c664  mov     eax, [rcx+150h]
0x14002c66a  jmp     short loc_14002C672
0x14002c66c  mov     eax, [rcx+108h]
0x14002c672  mov     [rdi+28h], eax
0x14002c675  call    SecReleaseProcessContext
0x14002c67a  mov     rcx, [rsp+48h+Process]; Object
0x14002c67f  test    rcx, rcx
0x14002c682  jz      short loc_14002C690
0x14002c684  call    cs:__imp_ObfDereferenceObject
0x14002c68b  nop     dword ptr [rax+rax+00h]
0x14002c690  mov     rcx, [rsp+48h+var_18]
0x14002c695  xor     rcx, rsp; StackCookie
0x14002c698  call    __security_check_cookie
0x14002c69d  mov     rbx, [rsp+48h+arg_8]
0x14002c6a2  mov     rsi, [rsp+48h+arg_10]
0x14002c6a7  add     rsp, 40h
0x14002c6ab  pop     rdi
0x14002c6ac  retn
```
