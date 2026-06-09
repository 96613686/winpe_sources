# CModule::InitWindowedSwapEffectUpgrade(void)

- ea: `0x180065c44`
- end: `0x180065edc`
- name: `?InitWindowedSwapEffectUpgrade@CModule@@QEAAXXZ`
- size: `664`
- prototype: `void __fastcall(CModule *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180066040`

## callees

- `0x18000c6b0`
- `0x18001c7a4`
- `0x18001c934`
- `0x180055e80`
- `0x180065c44`

## import_xrefs

- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryUserGlobalSettings` at `0x180065e17`
- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryUserGlobalSettings` at `0x180065e17`
- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryDirectXDatabaseConfig` at `0x180065ded`
- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryDirectXDatabaseConfig` at `0x180065ded`
- `ext-ms-win-dx-dxdbhelper-l1-1-2!__imp_QueryFullPreferenceData` at `0x180065d0d`
- `ext-ms-win-dx-dxdbhelper-l1-1-2!__imp_QueryFullPreferenceData` at `0x180065d0d`

## string_xrefs

- `0x180065d17`: `Unexpected failure during QueryFullPreferenceData for per-app DX_DATABASE_QUERY_TYPE_SWAPEFFECTUPGRADE_ENABLE.`
- `0x180065e21`: `Unexpected failure during QueryUserGlobalSettings for DX_DATABASE_QUERY_TYPE_SWAPEFFECTUPGRADE_ENABLE.`

## pseudocode

```c
void __fastcall CModule::InitWindowedSwapEffectUpgrade(CModule *this)
{
  int v2; // edi
  char v3; // si
  bool IsWindowedSwapEffectUpgradeRequired; // r14
  int v5; // eax
  CModule *v6; // rcx
  int v7; // eax
  int v8; // ecx
  char v9; // al
  int v10; // ecx
  int v11; // edi
  int v12; // eax
  CModule *v13; // rcx
  int v14; // ecx
  bool v15; // al
  unsigned __int64 v16; // [rsp+80h] [rbp+40h] BYREF
  int v17; // [rsp+88h] [rbp+48h] BYREF
  int v18; // [rsp+90h] [rbp+50h] BYREF

  v2 = 7;
  v16 = 7;
  v3 = 0;
  if ( (unsigned int)CompatValueImpl("WindowedSwapEffectUpgradeOverride", &v16, 0) && v16 < 3 )
  {
    v2 = v16;
    v3 = 1;
    *((_WORD *)this + 259) = 3;
  }
  CompatValueOrDefault("WindowedSwapEffectUpgrade", 1u, 0);
  if ( !*((_BYTE *)this + 488) || v3 && *((_DWORD *)this + 128) != v2 )
  {
    IsWindowedSwapEffectUpgradeRequired = CModule::IsWindowedSwapEffectUpgradeRequired(this);
    if ( !*((_BYTE *)this + 504) )
    {
      LODWORD(v16) = 119;
      v5 = QueryFullPreferenceData(10, 0, 0, 0, &v16, 4, 0);
      if ( v5 >= 0 )
      {
        v7 = v16;
      }
      else
      {
        CModule::RecordJournalImpl(
          v6,
          v5,
          "Unexpected failure during QueryFullPreferenceData for per-app DX_DATABASE_QUERY_TYPE_SWAPEFFECTUPGRADE_ENABLE.");
        v7 = v16 & 0xFFFF00FF | 0x100;
      }
      HIDWORD(v16) = v7;
      *(_DWORD *)((char *)this + 505) = *(_DWORD *)((char *)&v16 + 1);
      *(_WORD *)((char *)this + 509) = *(_WORD *)((char *)&v16 + 5);
      *((_BYTE *)this + 511) = HIBYTE(v16);
      v8 = v7 << 28 >> 28;
      *((_BYTE *)this + 504) = 1;
      if ( v8 < 3 || (v8 = (char)v7 >> 4, v8 < 3) )
      {
        *(_WORD *)((char *)this + 497) = *(_WORD *)((char *)&v16 + 1);
        *((_BYTE *)this + 499) = BYTE3(v16);
        *((_BYTE *)this + 496) = 1;
        *((_DWORD *)this + 125) = v8;
      }
    }
    v9 = *((_BYTE *)this + 496);
    if ( v3 )
    {
      v10 = 0;
      if ( !v9 )
      {
        *((_DWORD *)this + 128) = v2;
        v10 = v2;
      }
    }
    else
    {
      if ( v9 )
      {
        v10 = *((_DWORD *)this + 125);
      }
      else
      {
        v18 = 4;
        v17 = 0;
        v11 = 1;
        if ( (int)QueryDirectXDatabaseConfig(5, 0, 0, 0, &v17, &v18) >= 0 )
          v11 = v17 & 1;
        LODWORD(v16) = v11;
        v12 = QueryUserGlobalSettings(10, RecordJournal, &v16);
        if ( v12 >= 0 )
        {
          v14 = v16;
        }
        else
        {
          CModule::RecordJournalImpl(
            v13,
            v12,
            "Unexpected failure during QueryUserGlobalSettings for DX_DATABASE_QUERY_TYPE_SWAPEFFECTUPGRADE_ENABLE.");
          v14 = v16 & 0xFFFFFFF0;
        }
        v10 = v14 << 28 >> 28;
      }
      *((_WORD *)this + 259) = 1;
      if ( IsWindowedSwapEffectUpgradeRequired && !v10 )
      {
        v10 = 1;
        *((_BYTE *)this + 516) = 1;
        *((_WORD *)this + 259) = 4;
      }
      v15 = *((_BYTE *)this + 504) && (*((_DWORD *)this + 127) & 0x200) != 0;
      if ( v10 && !IsWindowedSwapEffectUpgradeRequired && !v15 && (*((_BYTE *)this + 528) & 1) == 0 )
      {
        v10 = 0;
        *((_WORD *)this + 259) = 2;
      }
    }
    *(_WORD *)((char *)this + 489) = *(_WORD *)((char *)&v16 + 1);
    *((_BYTE *)this + 491) = BYTE3(v16);
    *((_BYTE *)this + 488) = 1;
    *((_DWORD *)this + 123) = v10;
  }
}

```

## disassembly

```asm
0x180065c44  push    rbp
0x180065c46  push    rbx
0x180065c47  push    rsi
0x180065c48  push    rdi
0x180065c49  push    r12
0x180065c4b  push    r13
0x180065c4d  push    r14
0x180065c4f  mov     rbp, rsp
0x180065c52  sub     rsp, 40h
0x180065c56  mov     rbx, rcx
0x180065c59  lea     rdx, [rbp+arg_0]; unsigned __int64 *
0x180065c5d  mov     edi, 7
0x180065c62  lea     rcx, aWindowedswapef_0; "WindowedSwapEffectUpgradeOverride"
0x180065c69  xor     r8d, r8d; bool
0x180065c6c  mov     [rbp+arg_0], rdi
0x180065c70  xor     sil, sil
0x180065c73  call    ?CompatValueImpl@@YAHPEBDPEA_K_N@Z; CompatValueImpl(char const *,unsigned __int64 *,bool)
0x180065c78  lea     r13d, [rdi-4]
0x180065c7c  lea     r12d, [rdi-6]
0x180065c80  test    eax, eax
0x180065c82  jz      short loc_180065C98
0x180065c84  cmp     [rbp+arg_0], r13
0x180065c88  jnb     short loc_180065C98
0x180065c8a  mov     edi, dword ptr [rbp+arg_0]
0x180065c8d  mov     sil, r12b
0x180065c90  mov     [rbx+206h], r13w
0x180065c98  xor     r8d, r8d; bool
0x180065c9b  lea     rcx, aWindowedswapef; "WindowedSwapEffectUpgrade"
0x180065ca2  mov     rdx, r12; unsigned __int64
0x180065ca5  call    ?CompatValueOrDefault@@YA_KPEBD_K_N@Z; CompatValueOrDefault(char const *,unsigned __int64,bool)
0x180065caa  cmp     byte ptr [rbx+1E8h], 0
0x180065cb1  jz      short loc_180065CC8
0x180065cb3  test    sil, sil
0x180065cb6  jz      loc_180065ECD
0x180065cbc  cmp     [rbx+200h], edi
0x180065cc2  jz      loc_180065ECD
0x180065cc8  mov     rcx, rbx; this
0x180065ccb  call    ?IsWindowedSwapEffectUpgradeRequired@CModule@@QEAA_NXZ; CModule::IsWindowedSwapEffectUpgradeRequired(void)
0x180065cd0  cmp     byte ptr [rbx+1F8h], 0
0x180065cd7  mov     r14b, al
0x180065cda  mov     ecx, 4
0x180065cdf  jnz     loc_180065D9D
0x180065ce5  xor     edx, edx
0x180065ce7  mov     [rsp+40h+var_10], 0
0x180065cf0  mov     dword ptr [rsp+40h+var_18], ecx
0x180065cf4  lea     rax, [rbp+arg_0]
0x180065cf8  xor     r9d, r9d
0x180065cfb  mov     dword ptr [rbp+arg_0], 77h ; 'w'
0x180065d02  xor     r8d, r8d
0x180065d05  mov     [rsp+40h+var_20], rax
0x180065d0a  lea     ecx, [rdx+0Ah]
0x180065d0d  call    cs:__imp_QueryFullPreferenceData
0x180065d13  test    eax, eax
0x180065d15  jns     short loc_180065D33
0x180065d17  lea     r8, aUnexpectedFail_6; "Unexpected failure during QueryFullPref"...
0x180065d1e  mov     edx, eax; unsigned int
0x180065d20  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180065d25  mov     eax, dword ptr [rbp+arg_0]
0x180065d28  and     eax, 0FFFF01FFh
0x180065d2d  bts     eax, 8
0x180065d31  jmp     short loc_180065D36
0x180065d33  mov     eax, dword ptr [rbp+arg_0]
0x180065d36  mov     dword ptr [rbp+arg_0+4], eax
0x180065d39  mov     ecx, dword ptr [rbp+arg_0+1]
0x180065d3c  mov     [rbx+1F9h], ecx
0x180065d42  movzx   ecx, word ptr [rbp+arg_0+5]
0x180065d46  mov     [rbx+1FDh], cx
0x180065d4d  mov     cl, byte ptr [rbp+arg_0+7]
0x180065d50  mov     [rbx+1FFh], cl
0x180065d56  mov     ecx, eax
0x180065d58  shl     ecx, 1Ch
0x180065d5b  sar     ecx, 1Ch
0x180065d5e  mov     [rbx+1F8h], r12b
0x180065d65  cmp     ecx, r13d
0x180065d68  jl      short loc_180065D77
0x180065d6a  mov     ecx, eax
0x180065d6c  shl     ecx, 18h
0x180065d6f  sar     ecx, 1Ch
0x180065d72  cmp     ecx, r13d
0x180065d75  jge     short loc_180065D98
0x180065d77  movzx   eax, word ptr [rbp+arg_0+1]
0x180065d7b  mov     [rbx+1F1h], ax
0x180065d82  mov     al, byte ptr [rbp+arg_0+3]
0x180065d85  mov     [rbx+1F3h], al
0x180065d8b  mov     [rbx+1F0h], r12b
0x180065d92  mov     [rbx+1F4h], ecx
0x180065d98  mov     ecx, 4
0x180065d9d  mov     al, [rbx+1F0h]
0x180065da3  test    sil, sil
0x180065da6  jz      short loc_180065DBF
0x180065da8  xor     ecx, ecx
0x180065daa  test    al, al
0x180065dac  jnz     loc_180065EAC
0x180065db2  mov     [rbx+200h], edi
0x180065db8  mov     ecx, edi
0x180065dba  jmp     loc_180065EAC
0x180065dbf  test    al, al
0x180065dc1  jnz     short loc_180065E42
0x180065dc3  xor     edx, edx
0x180065dc5  mov     [rbp+arg_10], ecx
0x180065dc8  lea     rax, [rbp+arg_10]
0x180065dcc  mov     [rbp+arg_8], 0
0x180065dd3  mov     [rsp+40h+var_18], rax
0x180065dd8  xor     r9d, r9d
0x180065ddb  lea     rax, [rbp+arg_8]
0x180065ddf  xor     r8d, r8d
0x180065de2  lea     ecx, [rdx+5]
0x180065de5  mov     [rsp+40h+var_20], rax
0x180065dea  mov     edi, r12d
0x180065ded  call    cs:__imp_QueryDirectXDatabaseConfig
0x180065df3  test    eax, eax
0x180065df5  js      short loc_180065DFE
0x180065df7  movzx   edi, byte ptr [rbp+arg_8]
0x180065dfb  and     edi, r12d
0x180065dfe  mov     dword ptr [rbp+arg_0], edi
0x180065e01  lea     r8, [rbp+arg_0]
0x180065e05  mov     edi, 4
0x180065e0a  lea     rdx, ?RecordJournal@@YAXIPEBD_N@Z; RecordJournal(uint,char const *,bool)
0x180065e11  mov     r9d, edi
0x180065e14  lea     ecx, [rdi+6]
0x180065e17  call    cs:__imp_QueryUserGlobalSettings
0x180065e1d  test    eax, eax
0x180065e1f  jns     short loc_180065E37
0x180065e21  lea     r8, aUnexpectedFail_8; "Unexpected failure during QueryUserGlob"...
0x180065e28  mov     edx, eax; unsigned int
0x180065e2a  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180065e2f  mov     ecx, dword ptr [rbp+arg_0]
0x180065e32  and     ecx, 0FFFFFFF0h
0x180065e35  jmp     short loc_180065E3A
0x180065e37  mov     ecx, dword ptr [rbp+arg_0]
0x180065e3a  shl     ecx, 1Ch
0x180065e3d  sar     ecx, 1Ch
0x180065e40  jmp     short loc_180065E4D
0x180065e42  mov     ecx, [rbx+1F4h]
0x180065e48  mov     edi, 4
0x180065e4d  mov     [rbx+206h], r12w
0x180065e55  test    r14b, r14b
0x180065e58  jz      short loc_180065E6F
0x180065e5a  test    ecx, ecx
0x180065e5c  jnz     short loc_180065E6F
0x180065e5e  mov     ecx, r12d
0x180065e61  mov     [rbx+204h], r12b
0x180065e68  mov     [rbx+206h], di
0x180065e6f  cmp     byte ptr [rbx+1F8h], 0
0x180065e76  jz      short loc_180065E89
0x180065e78  test    dword ptr [rbx+1FCh], 200h
0x180065e82  jz      short loc_180065E89
0x180065e84  mov     al, r12b
0x180065e87  jmp     short loc_180065E8B
0x180065e89  xor     al, al
0x180065e8b  test    ecx, ecx
0x180065e8d  jz      short loc_180065EAC
0x180065e8f  test    r14b, r14b
0x180065e92  jnz     short loc_180065EAC
0x180065e94  test    al, al
0x180065e96  jnz     short loc_180065EAC
0x180065e98  test    [rbx+210h], r12b
0x180065e9f  jnz     short loc_180065EAC
0x180065ea1  xor     ecx, ecx
0x180065ea3  mov     word ptr [rbx+206h], 2
0x180065eac  movzx   eax, word ptr [rbp+arg_0+1]
0x180065eb0  mov     [rbx+1E9h], ax
0x180065eb7  mov     al, byte ptr [rbp+arg_0+3]
0x180065eba  mov     [rbx+1EBh], al
0x180065ec0  mov     [rbx+1E8h], r12b
0x180065ec7  mov     [rbx+1ECh], ecx
0x180065ecd  add     rsp, 40h
0x180065ed1  pop     r14
0x180065ed3  pop     r13
0x180065ed5  pop     r12
0x180065ed7  pop     rdi
0x180065ed8  pop     rsi
0x180065ed9  pop     rbx
0x180065eda  pop     rbp
0x180065edb  retn
```
