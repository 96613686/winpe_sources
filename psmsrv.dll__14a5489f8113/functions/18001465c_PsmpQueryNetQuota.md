# PsmpQueryNetQuota

- ea: `0x18001465c`
- end: `0x180014708`
- name: `PsmpQueryNetQuota`
- size: `172`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003504`
- `0x18000f790`

## callees

- `0x18001465c`
- `0x1800179d8`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x18001469d`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18001469d`
- `NduProv!__imp_NduQueryAppToken` at `0x1800146be`
- `NduProv!__imp_NduQueryAppToken` at `0x1800146be`

## pseudocode

```c
__int64 __fastcall PsmpQueryNetQuota(__int64 a1)
{
  bool v1; // zf
  int v3; // eax
  __int64 v4; // rcx
  int v5; // eax
  unsigned int v7; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF
  __int64 v9; // [rsp+50h] [rbp+18h] BYREF

  v1 = *(_QWORD *)(a1 + 232) == 0;
  v9 = 0;
  v7 = 0;
  if ( !v1 )
  {
    v8 = 0;
    v3 = RtlRunOnceExecuteOnce(&PsmpNetInit, PsmpNetInitializeCallback, 0, &v8);
    v4 = 0;
    if ( v3 >= 0 )
      v4 = v8;
    v5 = NduQueryAppToken(v4, *(_QWORD *)(a1 + 232), &v7, &v9);
    if ( !v5 )
      return v7;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_iD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_87e93bff43cf31b66581a1de2c4b3e60_Traceguids,
        *(_QWORD *)(a1 + 96),
        v5);
  }
  return 0;
}

```

## disassembly

```asm
0x18001465c  mov     rax, rsp
0x18001465f  push    rbx
0x180014660  sub     rsp, 30h
0x180014664  cmp     qword ptr [rcx+0E8h], 0
0x18001466c  mov     rbx, rcx
0x18001466f  mov     qword ptr [rax+18h], 0
0x180014677  mov     dword ptr [rax+8], 0
0x18001467e  jz      short loc_1800146D2
0x180014680  lea     r9, [rax+10h]
0x180014684  mov     qword ptr [rax+10h], 0
0x18001468c  xor     r8d, r8d
0x18001468f  lea     rdx, PsmpNetInitializeCallback
0x180014696  lea     rcx, PsmpNetInit
0x18001469d  call    cs:__imp_RtlRunOnceExecuteOnce
0x1800146a3  mov     rdx, [rbx+0E8h]
0x1800146aa  lea     r9, [rsp+38h+arg_10]
0x1800146af  xor     ecx, ecx
0x1800146b1  lea     r8, [rsp+38h+arg_0]
0x1800146b6  test    eax, eax
0x1800146b8  cmovns  rcx, [rsp+38h+arg_8]
0x1800146be  call    cs:__imp_NduQueryAppToken
0x1800146c4  test    eax, eax
0x1800146c6  jnz     short loc_1800146D6
0x1800146c8  mov     eax, [rsp+38h+arg_0]
0x1800146cc  add     rsp, 30h
0x1800146d0  pop     rbx
0x1800146d1  retn
0x1800146d2  xor     eax, eax
0x1800146d4  jmp     short loc_1800146CC
0x1800146d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146dd  test    byte ptr [rcx+1Ch], 1
0x1800146e1  jz      short loc_1800146D2
0x1800146e3  cmp     byte ptr [rcx+19h], 4
0x1800146e7  jb      short loc_1800146D2
0x1800146e9  mov     r9, [rbx+60h]
0x1800146ed  lea     r8, WPP_87e93bff43cf31b66581a1de2c4b3e60_Traceguids
0x1800146f4  mov     rcx, [rcx+10h]
0x1800146f8  mov     edx, 16h
0x1800146fd  mov     [rsp+38h+var_18], eax
0x180014701  call    WPP_SF_iD
0x180014706  jmp     short loc_1800146D2
```
