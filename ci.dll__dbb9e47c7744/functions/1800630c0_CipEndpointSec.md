# CipEndpointSec

- ea: `0x1800630c0`
- end: `0x1800633fa`
- name: `CipEndpointSec`
- size: `826`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, size_t Size@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x1800d9c50`

## callees

- `0x18001508c`
- `0x18002bf20`
- `0x18005e37c`
- `0x1800630c0`
- `0x180063400`
- `0x180063878`
- `0x180071ab8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180063173`
- `ntoskrnl!ExAllocatePool2` at `0x180063173`
- `ntoskrnl!ZwDeleteKey` at `0x1800632c8`
- `ntoskrnl!ZwDeleteKey` at `0x180063396`
- `ntoskrnl!ZwDeleteKey` at `0x1800632c8`
- `ntoskrnl!ZwDeleteKey` at `0x180063396`
- `ntoskrnl!PsGetCurrentProcess` at `0x180063122`
- `ntoskrnl!PsGetCurrentProcess` at `0x180063122`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800633c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800633c8`
- `ntoskrnl!ZwClose` at `0x1800633af`
- `ntoskrnl!ZwClose` at `0x1800633af`
- `ntoskrnl!ZwSetValueKey` at `0x180063303`
- `ntoskrnl!ZwSetValueKey` at `0x180063339`
- `ntoskrnl!ZwSetValueKey` at `0x180063303`
- `ntoskrnl!ZwSetValueKey` at `0x180063339`
- `ntoskrnl!PsGetProcessProtection` at `0x180063131`
- `ntoskrnl!PsGetProcessProtection` at `0x180063131`

## pseudocode

```c
__int64 __fastcall CipEndpointSec(void *Src, size_t Size, __int64 a3, unsigned int a4, _DWORD *a5)
{
  size_t v6; // rbx
  _DWORD *v8; // rsi
  __int64 CurrentProcess; // rax
  __int64 v10; // rdx
  char ProcessProtection; // al
  int MatchingEndpointSecEntry; // ebx
  _DWORD *Pool2; // rax
  unsigned int v14; // eax
  unsigned int v15; // edx
  int v16; // r14d
  __int16 v17; // cx
  char v18; // zf
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
  ProcessProtection = PsGetProcessProtection(CurrentProcess, v10);
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
  v14 = *((unsigned __int16 *)v8 + 4);
  if ( v14 < 0x10 )
    goto LABEL_5;
  v15 = *((unsigned __int16 *)v8 + 6);
  if ( v15 < 0x10 )
    goto LABEL_5;
  if ( v14 + *((unsigned __int16 *)v8 + 5) >= (unsigned int)v6 )
    goto LABEL_5;
  if ( v15 + *((unsigned __int16 *)v8 + 7) >= (unsigned int)v6 )
    goto LABEL_5;
  v16 = v8[1];
  if ( v16 >= 2 )
    goto LABEL_5;
  if ( !v16 )
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
        (v17 = *((_WORD *)v8 + 7)) == 0) )
  {
LABEL_5:
    MatchingEndpointSecEntry = -1073741811;
    goto LABEL_35;
  }
  Data = (char *)v8 + *((unsigned __int16 *)v8 + 6);
  v25[0] = v17;
  v25[1] = v17;
  MatchingEndpointSecEntry = CipValidateEndpointSecPolicyFile(v28, v25, &v21, &v30);
  if ( MatchingEndpointSecEntry < 0 )
    goto LABEL_34;
  v18 = v16 == 0;
  if ( v16 )
  {
LABEL_25:
    MatchingEndpointSecEntry = CipFindMatchingEndpointSecEntry((__int64)v25, v18, (__int64)&v30, &KeyHandle, v22);
    if ( MatchingEndpointSecEntry < 0 )
      goto LABEL_34;
    if ( v16 == 1 )
    {
      ZwDeleteKey(KeyHandle);
    }
    else if ( !v16 )
    {
      v19 = KeyHandle;
      MatchingEndpointSecEntry = ZwSetValueKey(KeyHandle, (PUNICODE_STRING)&ValueName, 0, 1u, Data, v25[0]);
      if ( MatchingEndpointSecEntry < 0 )
        goto LABEL_34;
      MatchingEndpointSecEntry = ZwSetValueKey(v19, (PUNICODE_STRING)&stru_180030570, 0, 1u, v28[1], LOWORD(v28[0]));
      if ( MatchingEndpointSecEntry < 0 )
        goto LABEL_34;
    }
    MatchingEndpointSecEntry = CiUpdatePolicies(0);
    if ( MatchingEndpointSecEntry >= 0 && !v16 )
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
0x1800630c0  push    rbx
0x1800630c2  push    rsi
0x1800630c3  push    rdi
0x1800630c4  push    r12
0x1800630c6  push    r13
0x1800630c8  push    r14
0x1800630ca  push    r15
0x1800630cc  sub     rsp, 90h
0x1800630d3  mov     rax, cs:__security_cookie
0x1800630da  xor     rax, rsp
0x1800630dd  mov     [rsp+0C8h+var_48], rax
0x1800630e5  mov     [rsp+0C8h+var_88], r9d
0x1800630ea  mov     r12, r8
0x1800630ed  mov     ebx, edx
0x1800630ef  mov     r15, rcx
0x1800630f2  mov     r13, [rsp+0C8h+arg_20]
0x1800630fa  xor     edi, edi
0x1800630fc  mov     esi, edi
0x1800630fe  xorps   xmm0, xmm0
0x180063101  movups  xmmword ptr [rsp+0C8h+var_70], xmm0
0x180063106  mov     [rsp+0C8h+var_97], dil
0x18006310b  mov     [rsp+0C8h+var_98], dil
0x180063110  movups  [rsp+0C8h+var_58], xmm0
0x180063115  mov     [rsp+0C8h+KeyHandle], rdi
0x18006311a  mov     [rsp+0C8h+var_7C], edi
0x18006311e  mov     [r13+0], edi
0x180063122  call    cs:__imp_PsGetCurrentProcess
0x180063129  nop     dword ptr [rax+rax+00h]
0x18006312e  mov     rcx, rax
0x180063131  call    cs:__imp_PsGetProcessProtection
0x180063138  nop     dword ptr [rax+rax+00h]
0x18006313d  mov     ecx, cs:g_CiOptions
0x180063143  test    cl, 8
0x180063146  jnz     short loc_180063156
0x180063148  cmp     al, 31h ; '1'
0x18006314a  jz      short loc_180063156
0x18006314c  mov     ebx, 0C0000022h
0x180063151  jmp     loc_18006338A
0x180063156  cmp     ebx, 14h
0x180063159  jnb     short loc_180063165
0x18006315b  mov     ebx, 0C000000Dh
0x180063160  jmp     loc_18006338A
0x180063165  mov     r8d, 63734943h
0x18006316b  mov     rdx, rbx
0x18006316e  mov     ecx, 101h
0x180063173  call    cs:__imp_ExAllocatePool2
0x18006317a  nop     dword ptr [rax+rax+00h]
0x18006317f  mov     rsi, rax
0x180063182  mov     [rsp+0C8h+var_60], rax
0x180063187  test    rax, rax
0x18006318a  jnz     short loc_180063196
0x18006318c  mov     ebx, 0C0000017h
0x180063191  jmp     loc_18006338A
0x180063196  mov     r8, rbx; Size
0x180063199  mov     rdx, r15; Src
0x18006319c  mov     rcx, rsi; void *
0x18006319f  call    RtlCopyFromUser
0x1800631a4  nop
0x1800631a5  mov     r15d, 1
0x1800631ab  cmp     [rsi], r15w
0x1800631af  jnz     short loc_18006315B
0x1800631b1  movzx   eax, word ptr [rsi+8]
0x1800631b5  cmp     eax, 10h
0x1800631b8  jb      short loc_18006315B
0x1800631ba  movzx   edx, word ptr [rsi+0Ch]
0x1800631be  cmp     edx, 10h
0x1800631c1  jb      short loc_18006315B
0x1800631c3  movzx   ecx, word ptr [rsi+0Ah]
0x1800631c7  add     ecx, eax
0x1800631c9  cmp     ecx, ebx
0x1800631cb  jnb     short loc_18006315B
0x1800631cd  movzx   ecx, word ptr [rsi+0Eh]
0x1800631d1  add     ecx, edx
0x1800631d3  cmp     ecx, ebx
0x1800631d5  jnb     short loc_18006315B
0x1800631d7  mov     r14d, [rsi+4]
0x1800631db  cmp     r14d, 2
0x1800631df  jge     loc_18006315B
0x1800631e5  test    r14d, r14d
0x1800631e8  jnz     short loc_18006320C
0x1800631ea  mov     dword ptr [r13+0], 8
0x1800631f2  cmp     [rsp+0C8h+var_88], 8
0x1800631f7  jnb     short loc_180063203
0x1800631f9  mov     ebx, 0C0000004h
0x1800631fe  jmp     loc_18006338A
0x180063203  test    r12, r12
0x180063206  jz      loc_18006315B
0x18006320c  cmp     [rsi+0Ah], di
0x180063210  jz      loc_18006315B
0x180063216  movzx   eax, word ptr [rsi+8]
0x18006321a  add     rax, rsi
0x18006321d  mov     [rsp+0C8h+var_70+8], rax
0x180063222  movzx   eax, word ptr [rsi+0Ah]
0x180063226  mov     word ptr [rsp+0C8h+var_70], ax
0x18006322b  movzx   eax, word ptr [rsi+0Ah]
0x18006322f  mov     word ptr [rsp+0C8h+var_70+2], ax
0x180063234  movzx   ecx, word ptr [rsi+0Eh]
0x180063238  test    cx, cx
0x18006323b  jz      loc_18006315B
0x180063241  movzx   eax, word ptr [rsi+0Ch]
0x180063245  add     rax, rsi
0x180063248  mov     [rsp+0C8h+var_78], rax
0x18006324d  mov     [rsp+0C8h+var_80], cx
0x180063252  mov     [rsp+0C8h+var_7E], cx
0x180063257  lea     r9, [rsp+0C8h+var_58]
0x18006325c  lea     r8, [rsp+0C8h+var_98]
0x180063261  lea     rdx, [rsp+0C8h+var_80]
0x180063266  lea     rcx, [rsp+0C8h+var_70]
0x18006326b  call    CipValidateEndpointSecPolicyFile
0x180063270  mov     ebx, eax
0x180063272  test    eax, eax
0x180063274  js      loc_180063386
0x18006327a  test    r14d, r14d
0x18006327d  jnz     short loc_180063293
0x18006327f  cmp     [rsp+0C8h+var_98], dil
0x180063284  jnz     short loc_180063290
0x180063286  mov     ebx, 0C0E90002h
0x18006328b  jmp     loc_18006338A
0x180063290  test    r14d, r14d
0x180063293  setz    dl
0x180063296  lea     rax, [rsp+0C8h+var_97]
0x18006329b  mov     [rsp+0C8h+Data], rax
0x1800632a0  lea     r9, [rsp+0C8h+KeyHandle]
0x1800632a5  lea     r8, [rsp+0C8h+var_58]
0x1800632aa  lea     rcx, [rsp+0C8h+var_80]
0x1800632af  call    CipFindMatchingEndpointSecEntry
0x1800632b4  mov     ebx, eax
0x1800632b6  test    eax, eax
0x1800632b8  js      loc_180063386
0x1800632be  cmp     r14d, r15d
0x1800632c1  jnz     short loc_1800632D6
0x1800632c3  mov     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x1800632c8  call    cs:__imp_ZwDeleteKey
0x1800632cf  nop     dword ptr [rax+rax+00h]
0x1800632d4  jmp     short loc_18006334B
0x1800632d6  test    r14d, r14d
0x1800632d9  jnz     short loc_18006334B
0x1800632db  movzx   eax, [rsp+0C8h+var_80]
0x1800632e0  mov     [rsp+0C8h+DataSize], eax; DataSize
0x1800632e4  mov     rax, [rsp+0C8h+var_78]
0x1800632e9  mov     [rsp+0C8h+Data], rax; Data
0x1800632ee  mov     r9d, r15d; Type
0x1800632f1  xor     r8d, r8d; TitleIndex
0x1800632f4  lea     rdx, ValueName; ValueName
0x1800632fb  mov     r15, [rsp+0C8h+KeyHandle]
0x180063300  mov     rcx, r15; KeyHandle
0x180063303  call    cs:__imp_ZwSetValueKey
0x18006330a  nop     dword ptr [rax+rax+00h]
0x18006330f  mov     ebx, eax
0x180063311  test    eax, eax
0x180063313  js      short loc_180063386
0x180063315  movzx   eax, word ptr [rsp+0C8h+var_70]
0x18006331a  mov     [rsp+0C8h+DataSize], eax; DataSize
0x18006331e  mov     rax, [rsp+0C8h+var_70+8]
0x180063323  mov     [rsp+0C8h+Data], rax; Data
0x180063328  lea     r9d, [r14+1]; Type
0x18006332c  xor     r8d, r8d; TitleIndex
0x18006332f  lea     rdx, stru_180030570; ValueName
0x180063336  mov     rcx, r15; KeyHandle
0x180063339  call    cs:__imp_ZwSetValueKey
0x180063340  nop     dword ptr [rax+rax+00h]
0x180063345  mov     ebx, eax
0x180063347  test    eax, eax
0x180063349  js      short loc_180063386
0x18006334b  xor     ecx, ecx
0x18006334d  call    CiUpdatePolicies
0x180063352  mov     ebx, eax
0x180063354  test    eax, eax
0x180063356  js      short loc_180063386
0x180063358  test    r14d, r14d
0x18006335b  jnz     short loc_180063386
0x18006335d  mov     rdx, [rsp+0C8h+KeyHandle]
0x180063362  mov     rcx, r12
0x180063365  call    RtlWriteULong64ToUser
0x18006336a  nop
0x18006336b  mov     [rsp+0C8h+KeyHandle], rdi
0x180063370  jmp     short loc_180063386
0x180063372  mov     ebx, eax
0x180063374  xor     edi, edi
0x180063376  mov     rsi, [rsp+0C8h+var_60]
0x18006337b  jmp     short loc_180063386
0x18006337d  mov     ebx, eax
0x18006337f  xor     edi, edi
0x180063381  mov     rsi, [rsp+0C8h+var_60]
0x180063386  test    ebx, ebx
0x180063388  jns     short loc_1800633A2
0x18006338a  cmp     [rsp+0C8h+var_97], dil
0x18006338f  jz      short loc_1800633A2
0x180063391  mov     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x180063396  call    cs:__imp_ZwDeleteKey
0x18006339d  nop     dword ptr [rax+rax+00h]
0x1800633a2  mov     r15, [rsp+0C8h+KeyHandle]
0x1800633a7  test    r15, r15
0x1800633aa  jz      short loc_1800633BB
0x1800633ac  mov     rcx, r15; Handle
0x1800633af  call    cs:__imp_ZwClose
0x1800633b6  nop     dword ptr [rax+rax+00h]
0x1800633bb  test    rsi, rsi
0x1800633be  jz      short loc_1800633D4
0x1800633c0  mov     edx, 63734943h; Tag
0x1800633c5  mov     rcx, rsi; P
0x1800633c8  call    cs:__imp_ExFreePoolWithTag
0x1800633cf  nop     dword ptr [rax+rax+00h]
0x1800633d4  mov     eax, ebx
0x1800633d6  mov     rcx, [rsp+0C8h+var_48]
0x1800633de  xor     rcx, rsp; StackCookie
0x1800633e1  call    __security_check_cookie
0x1800633e6  add     rsp, 90h
0x1800633ed  pop     r15
0x1800633ef  pop     r14
0x1800633f1  pop     r13
0x1800633f3  pop     r12
0x1800633f5  pop     rdi
0x1800633f6  pop     rsi
0x1800633f7  pop     rbx
0x1800633f8  retn
```
