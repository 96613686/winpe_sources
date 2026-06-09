# RfcommGetRegSettings

- ea: `0x1400326f8`
- end: `0x1400328e1`
- name: `RfcommGetRegSettings`
- size: `489`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140037080`

## callees

- `0x140003cb4`
- `0x1400041f8`
- `0x14001fc30`
- `0x1400326f8`
- `0x140034388`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400328b9`
- `ntoskrnl!ZwClose` at `0x1400328b9`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140032747`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140032747`

## string_xrefs

- `0x140032817`: `DisableRestrictedAccess`

## pseudocode

```c
__int64 __fastcall RfcommGetRegSettings(__int64 a1)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // edx
  unsigned int v5; // ebx
  const wchar_t *v6; // r12
  int KeyValueUlong; // eax
  int v8; // edx
  int v9; // r9d
  HANDLE Handle; // [rsp+48h] [rbp-30h] BYREF
  int v12; // [rsp+58h] [rbp-20h]

  Handle = 0;
  v2 = *(_QWORD *)(a1 + 40);
  v12 = 4;
  v3 = IoOpenDriverRegistryKey(v2, 0, 131097, 0, &Handle);
  v5 = v3;
  if ( v3 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        19,
        72,
        (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
        v3);
    goto LABEL_18;
  }
  v6 = L"DisableFirewall";
  KeyValueUlong = BthQueryKeyValueUlong(Handle);
  v5 = KeyValueUlong;
  if ( KeyValueUlong < 0 )
  {
    if ( KeyValueUlong != -1073741772 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_18;
      v9 = 74;
      goto LABEL_17;
    }
  }
  else
  {
    *(_BYTE *)(a1 + 48) = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Sd(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        19,
        73,
        (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
        (__int64)L"DisableFirewall",
        0);
  }
  v6 = L"DisableRestrictedAccess";
  KeyValueUlong = BthQueryKeyValueUlong(Handle);
  v5 = KeyValueUlong;
  if ( KeyValueUlong >= 0 )
  {
    LOBYTE(KeyValueUlong) = 0;
    *(_BYTE *)(a1 + 49) = 0;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_18;
    v9 = 75;
    goto LABEL_17;
  }
  if ( KeyValueUlong == -1073741772 )
  {
    v5 = 0;
    goto LABEL_18;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v9 = 76;
LABEL_17:
    WPP_RECORDER_SF_Sd(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      19,
      v9,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
      (__int64)v6,
      KeyValueUlong);
  }
LABEL_18:
  if ( Handle )
    ZwClose(Handle);
  return v5;
}

```

## disassembly

```asm
0x1400326f8  push    rbp
0x1400326fa  push    rbx
0x1400326fb  push    rsi
0x1400326fc  push    rdi
0x1400326fd  push    r12
0x1400326ff  push    r14
0x140032701  mov     rbp, rsp
0x140032704  sub     rsp, 78h
0x140032708  mov     rax, cs:__security_cookie
0x14003270f  xor     rax, rsp
0x140032712  mov     [rbp+var_10], rax
0x140032716  mov     r14, rcx
0x140032719  mov     [rbp+Handle], 0
0x140032721  mov     rcx, [rcx+28h]
0x140032725  lea     rax, [rbp+Handle]
0x140032729  xor     r9d, r9d
0x14003272c  mov     [rsp+78h+var_58], rax
0x140032731  xor     edx, edx
0x140032733  mov     [rbp+var_38], 0
0x14003273a  mov     r8d, 20019h
0x140032740  mov     [rbp+var_20], 4
0x140032747  call    cs:__imp_IoOpenDriverRegistryKey
0x14003274e  nop     dword ptr [rax+rax+00h]
0x140032753  mov     ebx, eax
0x140032755  test    eax, eax
0x140032757  jns     short loc_14003279C
0x140032759  lea     rdi, WPP_RECORDER_INITIALIZED
0x140032760  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140032767  jz      loc_1400328B0
0x14003276d  mov     rcx, cs:WPP_GLOBAL_Control
0x140032774  lea     rsi, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x14003277b  mov     r9d, 48h ; 'H'
0x140032781  mov     dword ptr [rsp+78h+var_50], eax
0x140032785  mov     [rsp+78h+var_58], rsi
0x14003278a  mov     rcx, [rcx+40h]
0x14003278e  lea     r8d, [r9-35h]
0x140032792  call    WPP_RECORDER_SF_d
0x140032797  jmp     loc_1400328B0
0x14003279c  mov     rcx, [rbp+Handle]; KeyHandle
0x1400327a0  lea     r12, aDisablefirewal; "DisableFirewall"
0x1400327a7  mov     rdx, r12
0x1400327aa  lea     r9, [rbp+var_38]
0x1400327ae  lea     r8, [rbp+var_28]
0x1400327b2  call    BthQueryKeyValueUlong
0x1400327b7  lea     rsi, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x1400327be  mov     ebx, eax
0x1400327c0  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400327c7  test    eax, eax
0x1400327c9  js      short loc_14003280C
0x1400327cb  cmp     [rbp+var_38], 1
0x1400327cf  setz    al
0x1400327d2  mov     [r14+30h], al
0x1400327d6  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400327dd  jz      short loc_140032813
0x1400327df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400327e6  mov     r9d, 49h ; 'I'
0x1400327ec  movzx   eax, al
0x1400327ef  mov     [rsp+78h+var_48], eax
0x1400327f3  mov     [rsp+78h+var_50], r12
0x1400327f8  mov     rcx, [rcx+40h]
0x1400327fc  lea     r8d, [r9-36h]
0x140032800  mov     [rsp+78h+var_58], rsi
0x140032805  call    WPP_RECORDER_SF_Sd
0x14003280a  jmp     short loc_140032813
0x14003280c  cmp     eax, 0C0000034h
0x140032811  jnz     short loc_14003286F
0x140032813  mov     rcx, [rbp+Handle]; KeyHandle
0x140032817  lea     r12, aDisablerestric; "DisableRestrictedAccess"
0x14003281e  mov     rdx, r12
0x140032821  lea     r9, [rbp+var_38]
0x140032825  lea     r8, [rbp+var_28]
0x140032829  call    BthQueryKeyValueUlong
0x14003282e  mov     ebx, eax
0x140032830  test    eax, eax
0x140032832  js      short loc_140032853
0x140032834  cmp     [rbp+var_38], 1
0x140032838  setz    al
0x14003283b  mov     [r14+31h], al
0x14003283f  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140032846  jz      short loc_1400328B0
0x140032848  movzx   eax, al
0x14003284b  mov     r9d, 4Bh ; 'K'
0x140032851  jmp     short loc_14003288C
0x140032853  cmp     eax, 0C0000034h
0x140032858  jnz     short loc_14003285E
0x14003285a  xor     ebx, ebx
0x14003285c  jmp     short loc_1400328B0
0x14003285e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140032865  jz      short loc_1400328B0
0x140032867  mov     r9d, 4Ch ; 'L'
0x14003286d  jmp     short loc_14003288C
0x14003286f  lea     rdi, WPP_RECORDER_INITIALIZED
0x140032876  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003287d  jz      short loc_1400328B0
0x14003287f  mov     r9d, 4Ah ; 'J'
0x140032885  lea     rsi, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x14003288c  mov     rcx, cs:WPP_GLOBAL_Control
0x140032893  mov     r8d, 13h
0x140032899  mov     [rsp+78h+var_48], eax
0x14003289d  mov     [rsp+78h+var_50], r12
0x1400328a2  mov     [rsp+78h+var_58], rsi
0x1400328a7  mov     rcx, [rcx+40h]
0x1400328ab  call    WPP_RECORDER_SF_Sd
0x1400328b0  mov     rcx, [rbp+Handle]; Handle
0x1400328b4  test    rcx, rcx
0x1400328b7  jz      short loc_1400328C5
0x1400328b9  call    cs:__imp_ZwClose
0x1400328c0  nop     dword ptr [rax+rax+00h]
0x1400328c5  mov     eax, ebx
0x1400328c7  mov     rcx, [rbp+var_10]
0x1400328cb  xor     rcx, rsp; StackCookie
0x1400328ce  call    __security_check_cookie
0x1400328d3  add     rsp, 78h
0x1400328d7  pop     r14
0x1400328d9  pop     r12
0x1400328db  pop     rdi
0x1400328dc  pop     rsi
0x1400328dd  pop     rbx
0x1400328de  pop     rbp
0x1400328df  retn
```
