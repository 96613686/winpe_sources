# CipEndpointSec

- ea: `0x180062880`
- end: `0x180062bba`
- name: `CipEndpointSec`
- size: `826`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, size_t Size@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x1800d5110`

## callees

- `0x1800151ac`
- `0x18002bef0`
- `0x18005dcb8`
- `0x180062880`
- `0x180062bc0`
- `0x180063038`
- `0x180070808`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180062933`
- `ntoskrnl!ExAllocatePool2` at `0x180062933`
- `ntoskrnl!ZwDeleteKey` at `0x180062a88`
- `ntoskrnl!ZwDeleteKey` at `0x180062b56`
- `ntoskrnl!ZwDeleteKey` at `0x180062a88`
- `ntoskrnl!ZwDeleteKey` at `0x180062b56`
- `ntoskrnl!PsGetCurrentProcess` at `0x1800628e2`
- `ntoskrnl!PsGetCurrentProcess` at `0x1800628e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062b88`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062b88`
- `ntoskrnl!ZwClose` at `0x180062b6f`
- `ntoskrnl!ZwClose` at `0x180062b6f`
- `ntoskrnl!ZwSetValueKey` at `0x180062ac3`
- `ntoskrnl!ZwSetValueKey` at `0x180062af9`
- `ntoskrnl!ZwSetValueKey` at `0x180062ac3`
- `ntoskrnl!ZwSetValueKey` at `0x180062af9`
- `ntoskrnl!PsGetProcessProtection` at `0x1800628f1`
- `ntoskrnl!PsGetProcessProtection` at `0x1800628f1`

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
      MatchingEndpointSecEntry = ZwSetValueKey(v19, (PUNICODE_STRING)&stru_1800304D0, 0, 1u, v28[1], LOWORD(v28[0]));
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
0x180062880  push    rbx
0x180062882  push    rsi
0x180062883  push    rdi
0x180062884  push    r12
0x180062886  push    r13
0x180062888  push    r14
0x18006288a  push    r15
0x18006288c  sub     rsp, 90h
0x180062893  mov     rax, cs:__security_cookie
0x18006289a  xor     rax, rsp
0x18006289d  mov     [rsp+0C8h+var_48], rax
0x1800628a5  mov     [rsp+0C8h+var_88], r9d
0x1800628aa  mov     r12, r8
0x1800628ad  mov     ebx, edx
0x1800628af  mov     r15, rcx
0x1800628b2  mov     r13, [rsp+0C8h+arg_20]
0x1800628ba  xor     edi, edi
0x1800628bc  mov     esi, edi
0x1800628be  xorps   xmm0, xmm0
0x1800628c1  movups  xmmword ptr [rsp+0C8h+var_70], xmm0
0x1800628c6  mov     [rsp+0C8h+var_97], dil
0x1800628cb  mov     [rsp+0C8h+var_98], dil
0x1800628d0  movups  [rsp+0C8h+var_58], xmm0
0x1800628d5  mov     [rsp+0C8h+KeyHandle], rdi
0x1800628da  mov     [rsp+0C8h+var_7C], edi
0x1800628de  mov     [r13+0], edi
0x1800628e2  call    cs:__imp_PsGetCurrentProcess
0x1800628e9  nop     dword ptr [rax+rax+00h]
0x1800628ee  mov     rcx, rax
0x1800628f1  call    cs:__imp_PsGetProcessProtection
0x1800628f8  nop     dword ptr [rax+rax+00h]
0x1800628fd  mov     ecx, cs:g_CiOptions
0x180062903  test    cl, 8
0x180062906  jnz     short loc_180062916
0x180062908  cmp     al, 31h ; '1'
0x18006290a  jz      short loc_180062916
0x18006290c  mov     ebx, 0C0000022h
0x180062911  jmp     loc_180062B4A
0x180062916  cmp     ebx, 14h
0x180062919  jnb     short loc_180062925
0x18006291b  mov     ebx, 0C000000Dh
0x180062920  jmp     loc_180062B4A
0x180062925  mov     r8d, 63734943h
0x18006292b  mov     rdx, rbx
0x18006292e  mov     ecx, 101h
0x180062933  call    cs:__imp_ExAllocatePool2
0x18006293a  nop     dword ptr [rax+rax+00h]
0x18006293f  mov     rsi, rax
0x180062942  mov     [rsp+0C8h+var_60], rax
0x180062947  test    rax, rax
0x18006294a  jnz     short loc_180062956
0x18006294c  mov     ebx, 0C0000017h
0x180062951  jmp     loc_180062B4A
0x180062956  mov     r8, rbx; Size
0x180062959  mov     rdx, r15; Src
0x18006295c  mov     rcx, rsi; void *
0x18006295f  call    RtlCopyFromUser
0x180062964  nop
0x180062965  mov     r15d, 1
0x18006296b  cmp     [rsi], r15w
0x18006296f  jnz     short loc_18006291B
0x180062971  movzx   eax, word ptr [rsi+8]
0x180062975  cmp     eax, 10h
0x180062978  jb      short loc_18006291B
0x18006297a  movzx   edx, word ptr [rsi+0Ch]
0x18006297e  cmp     edx, 10h
0x180062981  jb      short loc_18006291B
0x180062983  movzx   ecx, word ptr [rsi+0Ah]
0x180062987  add     ecx, eax
0x180062989  cmp     ecx, ebx
0x18006298b  jnb     short loc_18006291B
0x18006298d  movzx   ecx, word ptr [rsi+0Eh]
0x180062991  add     ecx, edx
0x180062993  cmp     ecx, ebx
0x180062995  jnb     short loc_18006291B
0x180062997  mov     r14d, [rsi+4]
0x18006299b  cmp     r14d, 2
0x18006299f  jge     loc_18006291B
0x1800629a5  test    r14d, r14d
0x1800629a8  jnz     short loc_1800629CC
0x1800629aa  mov     dword ptr [r13+0], 8
0x1800629b2  cmp     [rsp+0C8h+var_88], 8
0x1800629b7  jnb     short loc_1800629C3
0x1800629b9  mov     ebx, 0C0000004h
0x1800629be  jmp     loc_180062B4A
0x1800629c3  test    r12, r12
0x1800629c6  jz      loc_18006291B
0x1800629cc  cmp     [rsi+0Ah], di
0x1800629d0  jz      loc_18006291B
0x1800629d6  movzx   eax, word ptr [rsi+8]
0x1800629da  add     rax, rsi
0x1800629dd  mov     [rsp+0C8h+var_70+8], rax
0x1800629e2  movzx   eax, word ptr [rsi+0Ah]
0x1800629e6  mov     word ptr [rsp+0C8h+var_70], ax
0x1800629eb  movzx   eax, word ptr [rsi+0Ah]
0x1800629ef  mov     word ptr [rsp+0C8h+var_70+2], ax
0x1800629f4  movzx   ecx, word ptr [rsi+0Eh]
0x1800629f8  test    cx, cx
0x1800629fb  jz      loc_18006291B
0x180062a01  movzx   eax, word ptr [rsi+0Ch]
0x180062a05  add     rax, rsi
0x180062a08  mov     [rsp+0C8h+var_78], rax
0x180062a0d  mov     [rsp+0C8h+var_80], cx
0x180062a12  mov     [rsp+0C8h+var_7E], cx
0x180062a17  lea     r9, [rsp+0C8h+var_58]
0x180062a1c  lea     r8, [rsp+0C8h+var_98]
0x180062a21  lea     rdx, [rsp+0C8h+var_80]
0x180062a26  lea     rcx, [rsp+0C8h+var_70]
0x180062a2b  call    CipValidateEndpointSecPolicyFile
0x180062a30  mov     ebx, eax
0x180062a32  test    eax, eax
0x180062a34  js      loc_180062B46
0x180062a3a  test    r14d, r14d
0x180062a3d  jnz     short loc_180062A53
0x180062a3f  cmp     [rsp+0C8h+var_98], dil
0x180062a44  jnz     short loc_180062A50
0x180062a46  mov     ebx, 0C0E90002h
0x180062a4b  jmp     loc_180062B4A
0x180062a50  test    r14d, r14d
0x180062a53  setz    dl
0x180062a56  lea     rax, [rsp+0C8h+var_97]
0x180062a5b  mov     [rsp+0C8h+Data], rax
0x180062a60  lea     r9, [rsp+0C8h+KeyHandle]
0x180062a65  lea     r8, [rsp+0C8h+var_58]
0x180062a6a  lea     rcx, [rsp+0C8h+var_80]
0x180062a6f  call    CipFindMatchingEndpointSecEntry
0x180062a74  mov     ebx, eax
0x180062a76  test    eax, eax
0x180062a78  js      loc_180062B46
0x180062a7e  cmp     r14d, r15d
0x180062a81  jnz     short loc_180062A96
0x180062a83  mov     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x180062a88  call    cs:__imp_ZwDeleteKey
0x180062a8f  nop     dword ptr [rax+rax+00h]
0x180062a94  jmp     short loc_180062B0B
0x180062a96  test    r14d, r14d
0x180062a99  jnz     short loc_180062B0B
0x180062a9b  movzx   eax, [rsp+0C8h+var_80]
0x180062aa0  mov     [rsp+0C8h+DataSize], eax; DataSize
0x180062aa4  mov     rax, [rsp+0C8h+var_78]
0x180062aa9  mov     [rsp+0C8h+Data], rax; Data
0x180062aae  mov     r9d, r15d; Type
0x180062ab1  xor     r8d, r8d; TitleIndex
0x180062ab4  lea     rdx, ValueName; ValueName
0x180062abb  mov     r15, [rsp+0C8h+KeyHandle]
0x180062ac0  mov     rcx, r15; KeyHandle
0x180062ac3  call    cs:__imp_ZwSetValueKey
0x180062aca  nop     dword ptr [rax+rax+00h]
0x180062acf  mov     ebx, eax
0x180062ad1  test    eax, eax
0x180062ad3  js      short loc_180062B46
0x180062ad5  movzx   eax, word ptr [rsp+0C8h+var_70]
0x180062ada  mov     [rsp+0C8h+DataSize], eax; DataSize
0x180062ade  mov     rax, [rsp+0C8h+var_70+8]
0x180062ae3  mov     [rsp+0C8h+Data], rax; Data
0x180062ae8  lea     r9d, [r14+1]; Type
0x180062aec  xor     r8d, r8d; TitleIndex
0x180062aef  lea     rdx, stru_1800304D0; ValueName
0x180062af6  mov     rcx, r15; KeyHandle
0x180062af9  call    cs:__imp_ZwSetValueKey
0x180062b00  nop     dword ptr [rax+rax+00h]
0x180062b05  mov     ebx, eax
0x180062b07  test    eax, eax
0x180062b09  js      short loc_180062B46
0x180062b0b  xor     ecx, ecx
0x180062b0d  call    CiUpdatePolicies
0x180062b12  mov     ebx, eax
0x180062b14  test    eax, eax
0x180062b16  js      short loc_180062B46
0x180062b18  test    r14d, r14d
0x180062b1b  jnz     short loc_180062B46
0x180062b1d  mov     rdx, [rsp+0C8h+KeyHandle]
0x180062b22  mov     rcx, r12
0x180062b25  call    RtlWriteULong64ToUser
0x180062b2a  nop
0x180062b2b  mov     [rsp+0C8h+KeyHandle], rdi
0x180062b30  jmp     short loc_180062B46
0x180062b32  mov     ebx, eax
0x180062b34  xor     edi, edi
0x180062b36  mov     rsi, [rsp+0C8h+var_60]
0x180062b3b  jmp     short loc_180062B46
0x180062b3d  mov     ebx, eax
0x180062b3f  xor     edi, edi
0x180062b41  mov     rsi, [rsp+0C8h+var_60]
0x180062b46  test    ebx, ebx
0x180062b48  jns     short loc_180062B62
0x180062b4a  cmp     [rsp+0C8h+var_97], dil
0x180062b4f  jz      short loc_180062B62
0x180062b51  mov     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x180062b56  call    cs:__imp_ZwDeleteKey
0x180062b5d  nop     dword ptr [rax+rax+00h]
0x180062b62  mov     r15, [rsp+0C8h+KeyHandle]
0x180062b67  test    r15, r15
0x180062b6a  jz      short loc_180062B7B
0x180062b6c  mov     rcx, r15; Handle
0x180062b6f  call    cs:__imp_ZwClose
0x180062b76  nop     dword ptr [rax+rax+00h]
0x180062b7b  test    rsi, rsi
0x180062b7e  jz      short loc_180062B94
0x180062b80  mov     edx, 63734943h; Tag
0x180062b85  mov     rcx, rsi; P
0x180062b88  call    cs:__imp_ExFreePoolWithTag
0x180062b8f  nop     dword ptr [rax+rax+00h]
0x180062b94  mov     eax, ebx
0x180062b96  mov     rcx, [rsp+0C8h+var_48]
0x180062b9e  xor     rcx, rsp; StackCookie
0x180062ba1  call    __security_check_cookie
0x180062ba6  add     rsp, 90h
0x180062bad  pop     r15
0x180062baf  pop     r14
0x180062bb1  pop     r13
0x180062bb3  pop     r12
0x180062bb5  pop     rdi
0x180062bb6  pop     rsi
0x180062bb7  pop     rbx
0x180062bb8  retn
```
