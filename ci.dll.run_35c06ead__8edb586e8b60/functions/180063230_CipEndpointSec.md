# CipEndpointSec

- ea: `0x180063230`
- end: `0x18006356a`
- name: `CipEndpointSec`
- size: `826`
- prototype: `__int64 __fastcall(void *Src, size_t Size, __int64, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x1800d9c60`

## callees

- `0x1800150ec`
- `0x18002c0d0`
- `0x18005e31c`
- `0x180063230`
- `0x180063570`
- `0x1800639e8`
- `0x180071d98`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800632e3`
- `ntoskrnl!ExAllocatePool2` at `0x1800632e3`
- `ntoskrnl!ZwDeleteKey` at `0x180063438`
- `ntoskrnl!ZwDeleteKey` at `0x180063506`
- `ntoskrnl!ZwDeleteKey` at `0x180063438`
- `ntoskrnl!ZwDeleteKey` at `0x180063506`
- `ntoskrnl!PsGetCurrentProcess` at `0x180063292`
- `ntoskrnl!PsGetCurrentProcess` at `0x180063292`
- `ntoskrnl!ExFreePoolWithTag` at `0x180063538`
- `ntoskrnl!ExFreePoolWithTag` at `0x180063538`
- `ntoskrnl!ZwClose` at `0x18006351f`
- `ntoskrnl!ZwClose` at `0x18006351f`
- `ntoskrnl!ZwSetValueKey` at `0x180063473`
- `ntoskrnl!ZwSetValueKey` at `0x1800634a9`
- `ntoskrnl!ZwSetValueKey` at `0x180063473`
- `ntoskrnl!ZwSetValueKey` at `0x1800634a9`
- `ntoskrnl!PsGetProcessProtection` at `0x1800632a1`
- `ntoskrnl!PsGetProcessProtection` at `0x1800632a1`

## pseudocode

```c
__int64 __fastcall CipEndpointSec(void *Src, size_t Size, __int64 a3, unsigned int a4, _DWORD *a5)
{
  size_t v6; // rbx
  _DWORD *v8; // rsi
  __int64 CurrentProcess; // rax
  char ProcessProtection; // al
  NTSTATUS MatchingEndpointSecEntry; // ebx
  _DWORD *Pool2; // rax
  unsigned int v13; // eax
  unsigned int v14; // edx
  int v15; // r14d
  __int16 v16; // cx
  int v17; // edx
  bool v18; // zf
  HANDLE v19; // r15
  char v21; // [rsp+30h] [rbp-98h] BYREF
  char v22[7]; // [rsp+31h] [rbp-97h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-90h] BYREF
  unsigned int v24; // [rsp+40h] [rbp-88h]
  _WORD v25[2]; // [rsp+48h] [rbp-80h] BYREF
  int v26; // [rsp+4Ch] [rbp-7Ch]
  PVOID Data; // [rsp+50h] [rbp-78h]
  PVOID v28[2]; // [rsp+58h] [rbp-70h] BYREF
  void *v29; // [rsp+68h] [rbp-60h]
  __int128 v30; // [rsp+70h] [rbp-58h] BYREF

  v24 = a4;
  v6 = (unsigned int)Size;
  v8 = 0;
  *(_OWORD *)v28 = 0;
  v22[0] = 0;
  v21 = 0;
  v30 = 0;
  KeyHandle = 0;
  v26 = 0;
  *a5 = 0;
  CurrentProcess = PsGetCurrentProcess();
  ProcessProtection = PsGetProcessProtection(CurrentProcess);
  if ( (g_CiOptions & 8) == 0 && ProcessProtection != 49 )
  {
    MatchingEndpointSecEntry = -1073741790;
    goto LABEL_35;
  }
  if ( (unsigned int)v6 < 0x14 )
    goto LABEL_5;
  Pool2 = (_DWORD *)ExAllocatePool2(257, v6, 1668499779);
  v8 = Pool2;
  v29 = Pool2;
  if ( !Pool2 )
  {
    MatchingEndpointSecEntry = -1073741801;
    goto LABEL_35;
  }
  RtlCopyFromUser(Pool2, Src, v6);
  if ( *(_WORD *)v8 != 1 )
    goto LABEL_5;
  v13 = *((unsigned __int16 *)v8 + 4);
  if ( v13 < 0x10 )
    goto LABEL_5;
  v14 = *((unsigned __int16 *)v8 + 6);
  if ( v14 < 0x10 )
    goto LABEL_5;
  if ( v13 + *((unsigned __int16 *)v8 + 5) >= (unsigned int)v6 )
    goto LABEL_5;
  if ( v14 + *((unsigned __int16 *)v8 + 7) >= (unsigned int)v6 )
    goto LABEL_5;
  v15 = v8[1];
  if ( v15 >= 2 )
    goto LABEL_5;
  if ( !v15 )
  {
    *a5 = 8;
    if ( v24 < 8 )
    {
      MatchingEndpointSecEntry = -1073741820;
      goto LABEL_35;
    }
    if ( !a3 )
      goto LABEL_5;
  }
  if ( !*((_WORD *)v8 + 5)
    || (v28[1] = (char *)v8 + *((unsigned __int16 *)v8 + 4),
        LOWORD(v28[0]) = *((_WORD *)v8 + 5),
        WORD1(v28[0]) = *((_WORD *)v8 + 5),
        (v16 = *((_WORD *)v8 + 7)) == 0) )
  {
LABEL_5:
    MatchingEndpointSecEntry = -1073741811;
    goto LABEL_35;
  }
  Data = (char *)v8 + *((unsigned __int16 *)v8 + 6);
  v25[0] = v16;
  v25[1] = v16;
  MatchingEndpointSecEntry = CipValidateEndpointSecPolicyFile(v28, v25, &v21, &v30);
  if ( MatchingEndpointSecEntry < 0 )
    goto LABEL_34;
  v18 = v15 == 0;
  if ( v15 )
  {
LABEL_25:
    LOBYTE(v17) = v18;
    MatchingEndpointSecEntry = CipFindMatchingEndpointSecEntry(
                                 (unsigned int)v25,
                                 v17,
                                 (unsigned int)&v30,
                                 (unsigned int)&KeyHandle,
                                 (__int64)v22);
    if ( MatchingEndpointSecEntry < 0 )
      goto LABEL_34;
    if ( v15 == 1 )
    {
      ZwDeleteKey(KeyHandle);
    }
    else if ( !v15 )
    {
      v19 = KeyHandle;
      MatchingEndpointSecEntry = ZwSetValueKey(KeyHandle, (PUNICODE_STRING)&ValueName, 0, 1u, Data, v25[0]);
      if ( MatchingEndpointSecEntry < 0 )
        goto LABEL_34;
      MatchingEndpointSecEntry = ZwSetValueKey(v19, (PUNICODE_STRING)&stru_180030540, 0, 1u, v28[1], LOWORD(v28[0]));
      if ( MatchingEndpointSecEntry < 0 )
        goto LABEL_34;
    }
    MatchingEndpointSecEntry = CiUpdatePolicies(0);
    if ( MatchingEndpointSecEntry >= 0 && !v15 )
    {
      RtlWriteULong64ToUser(a3, KeyHandle);
      KeyHandle = 0;
    }
LABEL_34:
    if ( MatchingEndpointSecEntry >= 0 )
      goto LABEL_37;
    goto LABEL_35;
  }
  if ( v21 )
  {
    v18 = 1;
    goto LABEL_25;
  }
  MatchingEndpointSecEntry = -1058471934;
LABEL_35:
  if ( v22[0] )
    ZwDeleteKey(KeyHandle);
LABEL_37:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( v8 )
    ExFreePoolWithTag(v8, 0x63734943u);
  return (unsigned int)MatchingEndpointSecEntry;
}

```

## disassembly

```asm
0x180063230  push    rbx
0x180063232  push    rsi
0x180063233  push    rdi
0x180063234  push    r12
0x180063236  push    r13
0x180063238  push    r14
0x18006323a  push    r15
0x18006323c  sub     rsp, 90h
0x180063243  mov     rax, cs:__security_cookie
0x18006324a  xor     rax, rsp
0x18006324d  mov     [rsp+0C8h+var_48], rax
0x180063255  mov     [rsp+0C8h+var_88], r9d
0x18006325a  mov     r12, r8
0x18006325d  mov     ebx, edx
0x18006325f  mov     r15, rcx
0x180063262  mov     r13, [rsp+0C8h+arg_20]
0x18006326a  xor     edi, edi
0x18006326c  mov     esi, edi
0x18006326e  xorps   xmm0, xmm0
0x180063271  movups  xmmword ptr [rsp+0C8h+var_70], xmm0
0x180063276  mov     [rsp+0C8h+var_97], dil
0x18006327b  mov     [rsp+0C8h+var_98], dil
0x180063280  movups  [rsp+0C8h+var_58], xmm0
0x180063285  mov     [rsp+0C8h+KeyHandle], rdi
0x18006328a  mov     [rsp+0C8h+var_7C], edi
0x18006328e  mov     [r13+0], edi
0x180063292  call    cs:__imp_PsGetCurrentProcess
0x180063299  nop     dword ptr [rax+rax+00h]
0x18006329e  mov     rcx, rax
0x1800632a1  call    cs:__imp_PsGetProcessProtection
0x1800632a8  nop     dword ptr [rax+rax+00h]
0x1800632ad  mov     ecx, cs:g_CiOptions
0x1800632b3  test    cl, 8
0x1800632b6  jnz     short loc_1800632C6
0x1800632b8  cmp     al, 31h ; '1'
0x1800632ba  jz      short loc_1800632C6
0x1800632bc  mov     ebx, 0C0000022h
0x1800632c1  jmp     loc_1800634FA
0x1800632c6  cmp     ebx, 14h
0x1800632c9  jnb     short loc_1800632D5
0x1800632cb  mov     ebx, 0C000000Dh
0x1800632d0  jmp     loc_1800634FA
0x1800632d5  mov     r8d, 63734943h
0x1800632db  mov     rdx, rbx
0x1800632de  mov     ecx, 101h
0x1800632e3  call    cs:__imp_ExAllocatePool2
0x1800632ea  nop     dword ptr [rax+rax+00h]
0x1800632ef  mov     rsi, rax
0x1800632f2  mov     [rsp+0C8h+var_60], rax
0x1800632f7  test    rax, rax
0x1800632fa  jnz     short loc_180063306
0x1800632fc  mov     ebx, 0C0000017h
0x180063301  jmp     loc_1800634FA
0x180063306  mov     r8, rbx; Size
0x180063309  mov     rdx, r15; Src
0x18006330c  mov     rcx, rsi; void *
0x18006330f  call    RtlCopyFromUser
0x180063314  nop
0x180063315  mov     r15d, 1
0x18006331b  cmp     [rsi], r15w
0x18006331f  jnz     short loc_1800632CB
0x180063321  movzx   eax, word ptr [rsi+8]
0x180063325  cmp     eax, 10h
0x180063328  jb      short loc_1800632CB
0x18006332a  movzx   edx, word ptr [rsi+0Ch]
0x18006332e  cmp     edx, 10h
0x180063331  jb      short loc_1800632CB
0x180063333  movzx   ecx, word ptr [rsi+0Ah]
0x180063337  add     ecx, eax
0x180063339  cmp     ecx, ebx
0x18006333b  jnb     short loc_1800632CB
0x18006333d  movzx   ecx, word ptr [rsi+0Eh]
0x180063341  add     ecx, edx
0x180063343  cmp     ecx, ebx
0x180063345  jnb     short loc_1800632CB
0x180063347  mov     r14d, [rsi+4]
0x18006334b  cmp     r14d, 2
0x18006334f  jge     loc_1800632CB
0x180063355  test    r14d, r14d
0x180063358  jnz     short loc_18006337C
0x18006335a  mov     dword ptr [r13+0], 8
0x180063362  cmp     [rsp+0C8h+var_88], 8
0x180063367  jnb     short loc_180063373
0x180063369  mov     ebx, 0C0000004h
0x18006336e  jmp     loc_1800634FA
0x180063373  test    r12, r12
0x180063376  jz      loc_1800632CB
0x18006337c  cmp     [rsi+0Ah], di
0x180063380  jz      loc_1800632CB
0x180063386  movzx   eax, word ptr [rsi+8]
0x18006338a  add     rax, rsi
0x18006338d  mov     [rsp+0C8h+var_70+8], rax
0x180063392  movzx   eax, word ptr [rsi+0Ah]
0x180063396  mov     word ptr [rsp+0C8h+var_70], ax
0x18006339b  movzx   eax, word ptr [rsi+0Ah]
0x18006339f  mov     word ptr [rsp+0C8h+var_70+2], ax
0x1800633a4  movzx   ecx, word ptr [rsi+0Eh]
0x1800633a8  test    cx, cx
0x1800633ab  jz      loc_1800632CB
0x1800633b1  movzx   eax, word ptr [rsi+0Ch]
0x1800633b5  add     rax, rsi
0x1800633b8  mov     [rsp+0C8h+var_78], rax
0x1800633bd  mov     [rsp+0C8h+var_80], cx
0x1800633c2  mov     [rsp+0C8h+var_7E], cx
0x1800633c7  lea     r9, [rsp+0C8h+var_58]
0x1800633cc  lea     r8, [rsp+0C8h+var_98]
0x1800633d1  lea     rdx, [rsp+0C8h+var_80]
0x1800633d6  lea     rcx, [rsp+0C8h+var_70]
0x1800633db  call    CipValidateEndpointSecPolicyFile
0x1800633e0  mov     ebx, eax
0x1800633e2  test    eax, eax
0x1800633e4  js      loc_1800634F6
0x1800633ea  test    r14d, r14d
0x1800633ed  jnz     short loc_180063403
0x1800633ef  cmp     [rsp+0C8h+var_98], dil
0x1800633f4  jnz     short loc_180063400
0x1800633f6  mov     ebx, 0C0E90002h
0x1800633fb  jmp     loc_1800634FA
0x180063400  test    r14d, r14d
0x180063403  setz    dl
0x180063406  lea     rax, [rsp+0C8h+var_97]
0x18006340b  mov     [rsp+0C8h+Data], rax
0x180063410  lea     r9, [rsp+0C8h+KeyHandle]
0x180063415  lea     r8, [rsp+0C8h+var_58]
0x18006341a  lea     rcx, [rsp+0C8h+var_80]
0x18006341f  call    CipFindMatchingEndpointSecEntry
0x180063424  mov     ebx, eax
0x180063426  test    eax, eax
0x180063428  js      loc_1800634F6
0x18006342e  cmp     r14d, r15d
0x180063431  jnz     short loc_180063446
0x180063433  mov     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x180063438  call    cs:__imp_ZwDeleteKey
0x18006343f  nop     dword ptr [rax+rax+00h]
0x180063444  jmp     short loc_1800634BB
0x180063446  test    r14d, r14d
0x180063449  jnz     short loc_1800634BB
0x18006344b  movzx   eax, [rsp+0C8h+var_80]
0x180063450  mov     [rsp+0C8h+DataSize], eax; DataSize
0x180063454  mov     rax, [rsp+0C8h+var_78]
0x180063459  mov     [rsp+0C8h+Data], rax; Data
0x18006345e  mov     r9d, r15d; Type
0x180063461  xor     r8d, r8d; TitleIndex
0x180063464  lea     rdx, ValueName; ValueName
0x18006346b  mov     r15, [rsp+0C8h+KeyHandle]
0x180063470  mov     rcx, r15; KeyHandle
0x180063473  call    cs:__imp_ZwSetValueKey
0x18006347a  nop     dword ptr [rax+rax+00h]
0x18006347f  mov     ebx, eax
0x180063481  test    eax, eax
0x180063483  js      short loc_1800634F6
0x180063485  movzx   eax, word ptr [rsp+0C8h+var_70]
0x18006348a  mov     [rsp+0C8h+DataSize], eax; DataSize
0x18006348e  mov     rax, [rsp+0C8h+var_70+8]
0x180063493  mov     [rsp+0C8h+Data], rax; Data
0x180063498  lea     r9d, [r14+1]; Type
0x18006349c  xor     r8d, r8d; TitleIndex
0x18006349f  lea     rdx, stru_180030540; ValueName
0x1800634a6  mov     rcx, r15; KeyHandle
0x1800634a9  call    cs:__imp_ZwSetValueKey
0x1800634b0  nop     dword ptr [rax+rax+00h]
0x1800634b5  mov     ebx, eax
0x1800634b7  test    eax, eax
0x1800634b9  js      short loc_1800634F6
0x1800634bb  xor     ecx, ecx
0x1800634bd  call    CiUpdatePolicies
0x1800634c2  mov     ebx, eax
0x1800634c4  test    eax, eax
0x1800634c6  js      short loc_1800634F6
0x1800634c8  test    r14d, r14d
0x1800634cb  jnz     short loc_1800634F6
0x1800634cd  mov     rdx, [rsp+0C8h+KeyHandle]
0x1800634d2  mov     rcx, r12
0x1800634d5  call    RtlWriteULong64ToUser
0x1800634da  nop
0x1800634db  mov     [rsp+0C8h+KeyHandle], rdi
0x1800634e0  jmp     short loc_1800634F6
0x1800634e2  mov     ebx, eax
0x1800634e4  xor     edi, edi
0x1800634e6  mov     rsi, [rsp+0C8h+var_60]
0x1800634eb  jmp     short loc_1800634F6
0x1800634ed  mov     ebx, eax
0x1800634ef  xor     edi, edi
0x1800634f1  mov     rsi, [rsp+0C8h+var_60]
0x1800634f6  test    ebx, ebx
0x1800634f8  jns     short loc_180063512
0x1800634fa  cmp     [rsp+0C8h+var_97], dil
0x1800634ff  jz      short loc_180063512
0x180063501  mov     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x180063506  call    cs:__imp_ZwDeleteKey
0x18006350d  nop     dword ptr [rax+rax+00h]
0x180063512  mov     r15, [rsp+0C8h+KeyHandle]
0x180063517  test    r15, r15
0x18006351a  jz      short loc_18006352B
0x18006351c  mov     rcx, r15; Handle
0x18006351f  call    cs:__imp_ZwClose
0x180063526  nop     dword ptr [rax+rax+00h]
0x18006352b  test    rsi, rsi
0x18006352e  jz      short loc_180063544
0x180063530  mov     edx, 63734943h; Tag
0x180063535  mov     rcx, rsi; P
0x180063538  call    cs:__imp_ExFreePoolWithTag
0x18006353f  nop     dword ptr [rax+rax+00h]
0x180063544  mov     eax, ebx
0x180063546  mov     rcx, [rsp+0C8h+var_48]
0x18006354e  xor     rcx, rsp; StackCookie
0x180063551  call    __security_check_cookie
0x180063556  add     rsp, 90h
0x18006355d  pop     r15
0x18006355f  pop     r14
0x180063561  pop     r13
0x180063563  pop     r12
0x180063565  pop     rdi
0x180063566  pop     rsi
0x180063567  pop     rbx
0x180063568  retn
```
