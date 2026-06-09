# BiDeleteKey

- ea: `0x18003290c`
- end: `0x180032a20`
- name: `BiDeleteKey`
- size: `276`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18002c6b4`
- `0x18002d374`
- `0x18003290c`

## callees

- `0x18003223c`
- `0x18003290c`
- `0x180032bc4`
- `0x180032c9c`
- `0x180033914`
- `0x180039298`
- `0x18003997c`

## import_xrefs

- `ntdll!ZwDeleteKey` at `0x1800329db`
- `ntdll!ZwDeleteKey` at `0x1800329db`
- `ntdll!ZwClose` at `0x180032a06`
- `ntdll!ZwClose` at `0x180032a06`
- `ntdll!RtlFreeHeap` at `0x1800329aa`
- `ntdll!RtlFreeHeap` at `0x1800329aa`

## pseudocode

```c
__int64 __fastcall BiDeleteKey(__int64 a1)
{
  unsigned __int64 v1; // rbx
  int v2; // eax
  const WCHAR **v3; // r14
  unsigned int v4; // esi
  __int64 i; // rdi
  unsigned __int64 v6; // rdi
  unsigned int v7; // eax
  NTSTATUS v8; // eax
  unsigned int v9; // ebp
  unsigned int v11; // [rsp+50h] [rbp+8h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp+10h] BYREF
  PVOID P; // [rsp+60h] [rbp+18h] BYREF

  v11 = 0;
  v1 = a1 & 0xFFFFFFFFFFFFFFFDuLL;
  Handle = 0;
  P = 0;
  v2 = BiEnumerateSubKeys(a1 & 0xFFFFFFFFFFFFFFFDuLL, &P, &v11);
  v3 = (const WCHAR **)P;
  if ( v2 >= 0 )
  {
    v4 = v11;
    for ( i = 0; (unsigned int)i < v4; i = (unsigned int)(i + 1) )
    {
      if ( (int)BiOpenKey(v1, v3[i], 983103, &Handle) >= 0 && (int)BiDeleteKey(Handle) < 0 )
        BiCloseKey(Handle);
    }
  }
  if ( v3 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  if ( (v1 & 1) != 0 )
  {
    v6 = v1 & 0xFFFFFFFFFFFFFFFEuLL;
    v7 = ORDeleteKey(v1 & 0xFFFFFFFFFFFFFFFEuLL, 0);
    v8 = BiDosErrorToNtStatus(v7);
  }
  else
  {
    v8 = ZwDeleteKey((HANDLE)v1);
    v6 = v1 & 0xFFFFFFFFFFFFFFFEuLL;
  }
  v9 = v8;
  if ( v8 >= 0 )
  {
    if ( (v1 & 1) != 0 )
      ORCloseKey(v6);
    else
      ZwClose((HANDLE)v1);
  }
  return v9;
}

```

## disassembly

```asm
0x18003290c  mov     rax, rsp
0x18003290f  push    rbx
0x180032910  push    rbp
0x180032911  push    rsi
0x180032912  push    rdi
0x180032913  push    r14
0x180032915  sub     rsp, 20h
0x180032919  mov     rbx, rcx
0x18003291c  mov     dword ptr [rax+8], 0
0x180032923  and     rbx, 0FFFFFFFFFFFFFFFDh
0x180032927  mov     qword ptr [rax+10h], 0
0x18003292f  mov     rcx, rbx
0x180032932  mov     qword ptr [rax+18h], 0
0x18003293a  lea     r8, [rax+8]
0x18003293e  lea     rdx, [rax+18h]
0x180032942  call    BiEnumerateSubKeys
0x180032947  mov     r14, [rsp+48h+P]
0x18003294c  test    eax, eax
0x18003294e  js      short loc_180032993
0x180032950  mov     esi, [rsp+48h+arg_0]
0x180032954  xor     edi, edi
0x180032956  test    esi, esi
0x180032958  jz      short loc_180032993
0x18003295a  mov     rdx, [r14+rdi*8]
0x18003295e  lea     r9, [rsp+48h+Handle]
0x180032963  mov     r8d, 0F003Fh
0x180032969  mov     rcx, rbx
0x18003296c  call    BiOpenKey
0x180032971  test    eax, eax
0x180032973  js      short loc_18003298D
0x180032975  mov     rcx, [rsp+48h+Handle]
0x18003297a  call    BiDeleteKey
0x18003297f  test    eax, eax
0x180032981  jns     short loc_18003298D
0x180032983  mov     rcx, [rsp+48h+Handle]; Handle
0x180032988  call    BiCloseKey
0x18003298d  inc     edi
0x18003298f  cmp     edi, esi
0x180032991  jb      short loc_18003295A
0x180032993  test    r14, r14
0x180032996  jz      short loc_1800329B6
0x180032998  mov     rcx, gs:60h
0x1800329a1  mov     r8, r14; P
0x1800329a4  xor     edx, edx; Flags
0x1800329a6  mov     rcx, [rcx+30h]; HeapHandle
0x1800329aa  call    cs:__imp_RtlFreeHeap
0x1800329b1  nop     dword ptr [rax+rax+00h]
0x1800329b6  mov     rsi, rbx
0x1800329b9  and     esi, 1
0x1800329bc  jz      short loc_1800329D8
0x1800329be  mov     rdi, rbx
0x1800329c1  xor     edx, edx
0x1800329c3  and     rdi, 0FFFFFFFFFFFFFFFEh
0x1800329c7  mov     rcx, rdi
0x1800329ca  call    ORDeleteKey
0x1800329cf  mov     ecx, eax
0x1800329d1  call    BiDosErrorToNtStatus
0x1800329d6  jmp     short loc_1800329EE
0x1800329d8  mov     rcx, rbx; KeyHandle
0x1800329db  call    cs:__imp_ZwDeleteKey
0x1800329e2  nop     dword ptr [rax+rax+00h]
0x1800329e7  mov     rdi, rbx
0x1800329ea  and     rdi, 0FFFFFFFFFFFFFFFEh
0x1800329ee  mov     ebp, eax
0x1800329f0  test    eax, eax
0x1800329f2  js      short loc_180032A12
0x1800329f4  test    rsi, rsi
0x1800329f7  jz      short loc_180032A03
0x1800329f9  mov     rcx, rdi
0x1800329fc  call    ORCloseKey
0x180032a01  jmp     short loc_180032A12
0x180032a03  mov     rcx, rbx; Handle
0x180032a06  call    cs:__imp_ZwClose
0x180032a0d  nop     dword ptr [rax+rax+00h]
0x180032a12  mov     eax, ebp
0x180032a14  add     rsp, 20h
0x180032a18  pop     r14
0x180032a1a  pop     rdi
0x180032a1b  pop     rsi
0x180032a1c  pop     rbp
0x180032a1d  pop     rbx
0x180032a1e  retn
```
