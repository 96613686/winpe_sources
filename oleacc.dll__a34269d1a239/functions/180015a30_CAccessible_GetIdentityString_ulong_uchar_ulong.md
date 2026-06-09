# CAccessible::GetIdentityString(ulong,uchar * *,ulong *)

- ea: `0x180015a30`
- end: `0x180015aad`
- name: `?GetIdentityString@CAccessible@@UEAAJKPEAPEAEPEAK@Z`
- size: `125`
- prototype: `__int64 __fastcall(CAccessible *__hidden this, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180015a30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015a60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015a60`

## pseudocode

```c
__int64 __fastcall CAccessible::GetIdentityString(CAccessible *this, int a2, unsigned __int8 **a3, unsigned int *a4)
{
  __int64 v7; // rax
  unsigned __int8 *v9; // r8
  int v10; // edx
  int v11; // ecx
  __int64 result; // rax

  *a3 = 0;
  *a4 = 0;
  v7 = *((_QWORD *)this + 10);
  if ( !v7 || !*(_DWORD *)(v7 + 24) )
    return 2147500037LL;
  v9 = (unsigned __int8 *)CoTaskMemAlloc(0x10u);
  if ( !v9 )
    return 2147942414LL;
  v10 = *((_DWORD *)this + 12);
  v11 = *(_DWORD *)(*((_QWORD *)this + 10) + 28LL);
  result = 0;
  *(_DWORD *)v9 = -2147483647;
  *((_DWORD *)v9 + 1) = v10;
  *((_DWORD *)v9 + 2) = v11;
  *((_DWORD *)v9 + 3) = a2;
  *a3 = v9;
  *a4 = 16;
  return result;
}

```

## disassembly

```asm
0x180015a30  push    rbx
0x180015a32  push    rbp
0x180015a33  push    rsi
0x180015a34  push    rdi
0x180015a35  sub     rsp, 28h
0x180015a39  xor     eax, eax
0x180015a3b  mov     rdi, r9
0x180015a3e  mov     [r8], rax
0x180015a41  mov     rsi, r8
0x180015a44  mov     [r9], eax
0x180015a47  mov     ebp, edx
0x180015a49  mov     rax, [rcx+50h]
0x180015a4d  mov     rbx, rcx
0x180015a50  test    rax, rax
0x180015a53  jz      short loc_180015A9F
0x180015a55  cmp     dword ptr [rax+18h], 0
0x180015a59  jz      short loc_180015A9F
0x180015a5b  mov     ecx, 10h; cb
0x180015a60  call    cs:__imp_CoTaskMemAlloc
0x180015a66  mov     r8, rax
0x180015a69  test    rax, rax
0x180015a6c  jz      short loc_180015AA6
0x180015a6e  mov     rax, [rbx+50h]
0x180015a72  mov     edx, [rbx+30h]
0x180015a75  mov     ecx, [rax+1Ch]
0x180015a78  xor     eax, eax
0x180015a7a  mov     dword ptr [r8], 80000001h
0x180015a81  mov     [r8+4], edx
0x180015a85  mov     [r8+8], ecx
0x180015a89  mov     [r8+0Ch], ebp
0x180015a8d  mov     [rsi], r8
0x180015a90  mov     dword ptr [rdi], 10h
0x180015a96  add     rsp, 28h
0x180015a9a  pop     rdi
0x180015a9b  pop     rsi
0x180015a9c  pop     rbp
0x180015a9d  pop     rbx
0x180015a9e  retn
0x180015a9f  mov     eax, 80004005h
0x180015aa4  jmp     short loc_180015A96
0x180015aa6  mov     eax, 8007000Eh
0x180015aab  jmp     short loc_180015A96
```
