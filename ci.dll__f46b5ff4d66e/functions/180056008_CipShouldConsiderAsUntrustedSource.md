# CipShouldConsiderAsUntrustedSource

- ea: `0x180056008`
- end: `0x18005612d`
- name: `CipShouldConsiderAsUntrustedSource`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18009516c`

## callees

- `0x180056008`
- `0x180056134`
- `0x18009c8b0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1800560a3`
- `ntoskrnl!ObfDereferenceObject` at `0x1800560a3`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x180056112`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x180056112`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x1800560e1`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x1800560e1`

## pseudocode

```c
bool __fastcall CipShouldConsiderAsUntrustedSource(__int64 a1, struct _FILE_OBJECT *a2, int a3, _DWORD *a4)
{
  char v5; // si
  int v9; // ebx
  PVOID Object[5]; // [rsp+20h] [rbp-28h] BYREF
  char v11; // [rsp+58h] [rbp+10h] BYREF

  v5 = a3;
  if ( (a2->DeviceObject->Flags & 0x100) != 0 )
  {
    *a4 |= 0x8000u;
    return 0;
  }
  if ( (a3 & 0x20000000) != 0 || (a3 & 2) != 0 || (a3 & 0x40000000) != 0 || (g_CiOptions & 0x100) != 0 )
    return 0;
  Object[0] = 0;
  v11 = 0;
  if ( (int)CipIsCimBackedFile(a2, &v11, Object) >= 0 )
  {
    if ( v11 )
    {
      v9 = *(_DWORD *)(*((_QWORD *)Object[0] + 1) + 48LL);
      ObfDereferenceObject(Object[0]);
      if ( (v9 & 0x100) != 0 )
      {
        *a4 |= 0x8000u;
        return 0;
      }
    }
  }
  v11 = 0;
  if ( (int)CipGetVolumeFlags(a2) >= 0 )
  {
    if ( v11 )
    {
      *a4 |= 0x10000u;
      if ( (unsigned __int8)PsIsCurrentThreadInServerSilo() )
        return 0;
    }
  }
  return (v5 & 5) == 0 && ((v5 & 8) != 0 || (v5 & 0x10) == 0 && (unsigned int)PsIsProtectedProcessLight(a1));
}

```

## disassembly

```asm
0x180056008  mov     [rsp+arg_0], rbx
0x18005600d  mov     [rsp+arg_10], rbp
0x180056012  push    rsi
0x180056013  push    rdi
0x180056014  push    r14
0x180056016  sub     rsp, 30h
0x18005601a  mov     rax, [rdx+8]
0x18005601e  mov     rdi, r9
0x180056021  mov     esi, r8d
0x180056024  mov     rbp, rdx
0x180056027  mov     r14, rcx
0x18005602a  test    dword ptr [rax+30h], 100h
0x180056031  jz      short loc_18005604E
0x180056033  bts     dword ptr [r9], 0Fh
0x180056038  xor     al, al
0x18005603a  mov     rbx, [rsp+48h+arg_0]
0x18005603f  mov     rbp, [rsp+48h+arg_10]
0x180056044  add     rsp, 30h
0x180056048  pop     r14
0x18005604a  pop     rdi
0x18005604b  pop     rsi
0x18005604c  retn
0x18005604e  bt      esi, 1Dh
0x180056052  jb      short loc_180056038
0x180056054  test    sil, 2
0x180056058  jnz     short loc_180056038
0x18005605a  bt      esi, 1Eh
0x18005605e  jb      short loc_180056038
0x180056060  test    cs:g_CiOptions, 100h
0x18005606a  jnz     short loc_180056038
0x18005606c  lea     r8, [rsp+48h+Object]
0x180056071  mov     [rsp+48h+Object], 0
0x18005607a  lea     rdx, [rsp+48h+arg_8]
0x18005607f  mov     [rsp+48h+arg_8], 0
0x180056084  mov     rcx, rbp
0x180056087  call    CipIsCimBackedFile
0x18005608c  test    eax, eax
0x18005608e  js      short loc_1800560BE
0x180056090  cmp     [rsp+48h+arg_8], 0
0x180056095  jz      short loc_1800560BE
0x180056097  mov     rcx, [rsp+48h+Object]; Object
0x18005609c  mov     rax, [rcx+8]
0x1800560a0  mov     ebx, [rax+30h]
0x1800560a3  call    cs:__imp_ObfDereferenceObject
0x1800560aa  nop     dword ptr [rax+rax+00h]
0x1800560af  bt      ebx, 8
0x1800560b3  jnb     short loc_1800560BE
0x1800560b5  bts     dword ptr [rdi], 0Fh
0x1800560b9  jmp     loc_180056038
0x1800560be  lea     r8, [rsp+48h+arg_8]
0x1800560c3  mov     [rsp+48h+arg_8], 0
0x1800560c8  xor     edx, edx
0x1800560ca  mov     rcx, rbp; FileObject
0x1800560cd  call    CipGetVolumeFlags
0x1800560d2  test    eax, eax
0x1800560d4  js      short loc_1800560F5
0x1800560d6  cmp     [rsp+48h+arg_8], 0
0x1800560db  jz      short loc_1800560F5
0x1800560dd  bts     dword ptr [rdi], 10h
0x1800560e1  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x1800560e8  nop     dword ptr [rax+rax+00h]
0x1800560ed  test    al, al
0x1800560ef  jnz     loc_180056038
0x1800560f5  test    sil, 5
0x1800560f9  jnz     loc_180056038
0x1800560ff  test    sil, 8
0x180056103  jnz     short loc_180056126
0x180056105  test    sil, 10h
0x180056109  jnz     loc_180056038
0x18005610f  mov     rcx, r14
0x180056112  call    cs:__imp_PsIsProtectedProcessLight
0x180056119  nop     dword ptr [rax+rax+00h]
0x18005611e  test    eax, eax
0x180056120  jz      loc_180056038
0x180056126  mov     al, 1
0x180056128  jmp     loc_18005603A
```
