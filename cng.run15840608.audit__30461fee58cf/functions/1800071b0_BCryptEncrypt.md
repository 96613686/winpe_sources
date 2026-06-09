# BCryptEncrypt

- ea: `0x1800071b0`
- end: `0x180007435`
- name: `BCryptEncrypt`
- size: `645`
- prototype: `NTSTATUS __stdcall(BCRYPT_KEY_HANDLE hKey, PUCHAR pbInput, ULONG cbInput, void *pPaddingInfo, PUCHAR pbIV, ULONG cbIV, PUCHAR pbOutput, ULONG cbOutput, ULONG *pcbResult, ULONG dwFlags)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180006cf0`
- `0x18003e9dc`
- `0x18003ed70`

## callees

- `0x180003c70`
- `0x180003f70`
- `0x180006470`
- `0x1800071b0`
- `0x18000743c`
- `0x1800082b0`
- `0x1800577f0`
- `0x18005bbfc`
- `0x180068fa8`
- `0x18009d860`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180007278`
- `ntoskrnl!KeGetCurrentIrql` at `0x180007278`

## string_xrefs

- `0x180007257`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180007346`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180007391`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18009efb6`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptEncrypt(
        BCRYPT_KEY_HANDLE hKey,
        PUCHAR pbInput,
        ULONG cbInput,
        void *pPaddingInfo,
        PUCHAR pbIV,
        ULONG cbIV,
        PUCHAR pbOutput,
        ULONG cbOutput,
        ULONG *pcbResult,
        ULONG dwFlags)
{
  ULONG v10; // r10d
  PUCHAR v11; // r11
  NTSTATUS v13; // ebx
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // r9
  UCHAR *v17; // rsi
  __int64 (__fastcall *v18)(_QWORD, PUCHAR, _QWORD, void *, PUCHAR, ULONG, PUCHAR, ULONG, ULONG *, ULONG); // r14
  int v19; // eax
  int v21; // eax
  __int64 v22; // r9
  NTSTATUS Property; // eax
  int v24; // eax
  int v25; // eax
  __int64 v26; // r9
  UCHAR v27[4]; // [rsp+60h] [rbp-48h] BYREF
  int v28; // [rsp+64h] [rbp-44h] BYREF
  ULONG v29[16]; // [rsp+68h] [rbp-40h] BYREF

  v10 = cbInput;
  v28 = 0;
  v11 = pbInput;
  *(_DWORD *)v27 = 0;
  v29[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
  {
    WPP_SF_qqqdqdqD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      23,
      cbInput,
      hKey,
      pPaddingInfo,
      pbInput,
      cbInput,
      pbOutput,
      cbOutput,
      pcbResult,
      dwFlags);
    v10 = cbInput;
    v11 = pbInput;
  }
  if ( pcbResult )
  {
    if ( !hKey || *(_DWORD *)hKey < 0x20u || *((_DWORD *)hKey + 1) != 1431655762 )
      goto LABEL_8;
    if ( !*(_DWORD *)(*((_QWORD *)hKey + 1) + 32LL) )
    {
      if ( KeGetCurrentIrql() >= 2u )
      {
LABEL_8:
        v13 = -1073741816;
        v14 = 3922;
        v15 = 3221225480LL;
LABEL_9:
        DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v14);
        return v13;
      }
      v10 = cbInput;
      v11 = pbInput;
    }
    v16 = *((_QWORD *)hKey + 1);
    v17 = 0;
    if ( *(_DWORD *)(v16 + 36) == 1 )
    {
      v18 = *(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, void *, PUCHAR, ULONG, PUCHAR, ULONG, ULONG *, ULONG))(v16 + 96);
LABEL_15:
      v19 = v18(*((_QWORD *)hKey + 2), v11, v10, pPaddingInfo, pbIV, cbIV, pbOutput, cbOutput, pcbResult, dwFlags);
      v13 = v19;
      if ( v19 < 0 )
      {
        v14 = 4062;
        v15 = (unsigned int)v19;
        goto LABEL_9;
      }
      goto LABEL_16;
    }
    if ( *(_DWORD *)(v16 + 36) != 3 )
    {
      v13 = -1073741637;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          (_DWORD)pbInput,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          (unsigned int)"Status",
          187,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          137);
      return v13;
    }
    v21 = ShouldRouterPadEncryption(*(unsigned int *)(v16 + 440), dwFlags, &v28);
    v13 = v21;
    if ( v21 < 0 )
    {
      v14 = 3953;
      v15 = (unsigned int)v21;
      goto LABEL_9;
    }
    v18 = *(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, void *, PUCHAR, ULONG, PUCHAR, ULONG, ULONG *, ULONG))(v22 + 104);
    if ( !v28 )
      goto LABEL_15;
    Property = BCryptGetProperty(hKey, L"KeyStrength", v27, 4u, v29, 0);
    v13 = Property;
    if ( Property < 0 )
    {
      v14 = 3968;
      v15 = (unsigned int)Property;
      goto LABEL_9;
    }
    v10 = cbInput;
    v11 = pbInput;
    *(_DWORD *)v27 = (unsigned int)(*(_DWORD *)v27 + 7) >> 3;
    if ( !v28 )
      goto LABEL_15;
    if ( !pbOutput )
    {
      v24 = v18(*((_QWORD *)hKey + 2), pbInput, cbInput, 0, pbIV, cbIV, 0, cbOutput, pcbResult, 0);
      v13 = v24;
      if ( v24 < 0 )
      {
        v14 = 3998;
        v15 = (unsigned int)v24;
        goto LABEL_9;
      }
      goto LABEL_16;
    }
    v17 = (UCHAR *)MSCryptAlloc(*(unsigned int *)v27);
    if ( !v17 )
    {
      v13 = -1073741801;
      v14 = 4014;
      v15 = 3221225495LL;
      goto LABEL_9;
    }
    v25 = ApplyEncryptionPadding(dwFlags, pPaddingInfo, pbInput, cbInput, v17, *(_DWORD *)v27);
    v13 = v25;
    if ( v25 >= 0 )
    {
      v25 = v18(*((_QWORD *)hKey + 2), v17, cbOutput, 0, pbIV, cbIV, pbOutput, cbOutput, pcbResult, 0);
      v13 = v25;
      if ( v25 >= 0 )
      {
LABEL_16:
        v13 = 0;
        if ( !v17 )
          return v13;
LABEL_28:
        MSCryptFree(v17);
        return v13;
      }
      v26 = 4043;
    }
    else
    {
      v26 = 4027;
    }
    DebugTraceError((unsigned int)v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v26);
    goto LABEL_28;
  }
  v13 = -1073741811;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      (_DWORD)pbInput,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      74);
  return v13;
}

```

## disassembly

```asm
0x1800071b0  mov     [rsp+arg_18], r9
0x1800071b5  mov     [rsp+arg_10], r8d
0x1800071ba  mov     [rsp+arg_8], rdx
0x1800071bf  push    rbx
0x1800071c0  push    rbp
0x1800071c1  push    rdi
0x1800071c2  push    r12
0x1800071c4  push    r13
0x1800071c6  push    r14
0x1800071c8  push    r15
0x1800071ca  sub     rsp, 70h
0x1800071ce  xor     ebx, ebx
0x1800071d0  mov     r10d, r8d
0x1800071d3  mov     [rsp+0A8h+var_44], ebx
0x1800071d7  mov     r11, rdx
0x1800071da  mov     dword ptr [rsp+0A8h+var_48], ebx
0x1800071de  mov     rdi, rcx
0x1800071e1  mov     [rsp+0A8h+var_40], ebx
0x1800071e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071ec  lea     r14, WPP_GLOBAL_Control
0x1800071f3  mov     r13d, [rsp+0A8h+dwFlags]
0x1800071fb  mov     rbp, [rsp+0A8h+pcbResult]
0x180007203  mov     r12d, [rsp+0A8h+cbOutput]
0x18000720b  mov     r15, [rsp+0A8h+pbOutput]
0x180007213  cmp     rcx, r14
0x180007216  jz      short loc_180007223
0x180007218  mov     eax, [rcx+2Ch]
0x18000721b  test    al, 4
0x18000721d  jnz     loc_1800073A7
0x180007223  mov     [rsp+0A8h+arg_0], rsi
0x18000722b  test    rbp, rbp
0x18000722e  jz      loc_180007326
0x180007234  test    rdi, rdi
0x180007237  jz      short loc_180007247
0x180007239  cmp     dword ptr [rdi], 20h ; ' '
0x18000723c  jb      short loc_180007247
0x18000723e  cmp     dword ptr [rdi+4], 55555552h
0x180007245  jz      short loc_18000726F
0x180007247  mov     ebx, 0C0000008h
0x18000724c  mov     r9d, 0F52h
0x180007252  mov     ecx, 0C0000008h
0x180007257  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000725e  lea     rdx, aStatus; "Status"
0x180007265  call    DebugTraceError
0x18000726a  jmp     loc_18000730B
0x18000726f  mov     rax, [rdi+8]
0x180007273  cmp     [rax+20h], ebx
0x180007276  jnz     short loc_180007298
0x180007278  call    cs:__imp_KeGetCurrentIrql
0x18000727f  nop     dword ptr [rax+rax+00h]
0x180007284  cmp     al, 2
0x180007286  jnb     short loc_180007247
0x180007288  mov     r10d, [rsp+0A8h+arg_10]
0x180007290  mov     r11, [rsp+0A8h+arg_8]
0x180007298  mov     r9, [rdi+8]
0x18000729c  mov     rsi, rbx
0x18000729f  mov     ecx, [r9+24h]
0x1800072a3  sub     ecx, 1
0x1800072a6  jnz     loc_18000736C
0x1800072ac  mov     r14, [r9+60h]
0x1800072b0  mov     eax, [rsp+0A8h+cbIV]
0x1800072b7  mov     r8d, r10d
0x1800072ba  mov     r9, [rsp+0A8h+arg_18]
0x1800072c2  mov     rdx, r11
0x1800072c5  mov     rcx, [rdi+10h]
0x1800072c9  mov     dword ptr [rsp+0A8h+var_60], r13d
0x1800072ce  mov     [rsp+0A8h+var_68], rbp
0x1800072d3  mov     dword ptr [rsp+0A8h+var_70], r12d
0x1800072d8  mov     [rsp+0A8h+var_78], r15
0x1800072dd  mov     [rsp+0A8h+var_80], eax
0x1800072e1  mov     rax, [rsp+0A8h+pbIV]
0x1800072e9  mov     [rsp+0A8h+var_88], rax
0x1800072ee  mov     rax, r14
0x1800072f1  call    _guard_dispatch_icall
0x1800072f6  mov     ebx, eax
0x1800072f8  test    eax, eax
0x1800072fa  js      loc_18000741B
0x180007300  xor     ebx, ebx
0x180007302  test    rsi, rsi
0x180007305  jnz     loc_180007428
0x18000730b  mov     rsi, [rsp+0A8h+arg_0]
0x180007313  mov     eax, ebx
0x180007315  add     rsp, 70h
0x180007319  pop     r15
0x18000731b  pop     r14
0x18000731d  pop     r13
0x18000731f  pop     r12
0x180007321  pop     rdi
0x180007322  pop     rbp
0x180007323  pop     rbx
0x180007324  retn
0x180007326  mov     ebx, 0C000000Dh
0x18000732b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007332  cmp     rcx, r14
0x180007335  jz      short loc_18000730B
0x180007337  mov     eax, [rcx+2Ch]
0x18000733a  test    al, 1
0x18000733c  jz      short loc_18000730B
0x18000733e  mov     dword ptr [rsp+0A8h+var_78], 0F4Ah
0x180007346  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000734d  mov     qword ptr [rsp+0A8h+var_80], r8
0x180007352  mov     dword ptr [rsp+0A8h+var_88], 0C000000Dh
0x18000735a  mov     rcx, [rcx+18h]
0x18000735e  lea     r9, aStatus; "Status"
0x180007365  call    WPP_SF_sDsd
0x18000736a  jmp     short loc_18000730B
0x18000736c  cmp     ecx, 2
0x18000736f  jz      short loc_1800073F0
0x180007371  mov     ebx, 0C00000BBh
0x180007376  mov     rcx, cs:WPP_GLOBAL_Control
0x18000737d  cmp     rcx, r14
0x180007380  jz      short loc_18000730B
0x180007382  mov     eax, [rcx+2Ch]
0x180007385  test    al, 1
0x180007387  jz      short loc_18000730B
0x180007389  mov     dword ptr [rsp+0A8h+var_78], 0F89h
0x180007391  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007398  mov     qword ptr [rsp+0A8h+var_80], r8
0x18000739d  mov     dword ptr [rsp+0A8h+var_88], 0C00000BBh
0x1800073a5  jmp     short loc_18000735A
0x1800073a7  mov     rcx, [rcx+18h]
0x1800073ab  mov     edx, 17h
0x1800073b0  mov     [rsp+0A8h+var_58], r13d
0x1800073b5  mov     [rsp+0A8h+var_60], rbp
0x1800073ba  mov     dword ptr [rsp+0A8h+var_68], r12d
0x1800073bf  mov     [rsp+0A8h+var_70], r15
0x1800073c4  mov     dword ptr [rsp+0A8h+var_78], r8d
0x1800073c9  mov     qword ptr [rsp+0A8h+var_80], r11
0x1800073ce  mov     [rsp+0A8h+var_88], r9
0x1800073d3  mov     r9, rdi
0x1800073d6  call    WPP_SF_qqqdqdqD
0x1800073db  mov     r10d, [rsp+0A8h+arg_10]
0x1800073e3  mov     r11, [rsp+0A8h+arg_8]
0x1800073eb  jmp     loc_180007223
0x1800073f0  mov     ecx, [r9+1B8h]
0x1800073f7  lea     r8, [rsp+0A8h+var_44]
0x1800073fc  mov     edx, r13d
0x1800073ff  call    ShouldRouterPadEncryption
0x180007404  mov     ebx, eax
0x180007406  test    eax, eax
0x180007408  jns     loc_18009EE7E
0x18000740e  mov     r9d, 0F71h
0x180007414  mov     ecx, eax
0x180007416  jmp     loc_180007257
0x18000741b  mov     r9d, 0FDEh
0x180007421  mov     ecx, eax
0x180007423  jmp     loc_180007257
0x180007428  mov     rcx, rsi; P
0x18000742b  call    MSCryptFree
0x180007430  jmp     loc_18000730B
0x18009ee7e  mov     eax, [rsp+0A8h+var_44]
0x18009ee82  mov     r14, [r9+68h]
0x18009ee86  test    eax, eax
0x18009ee88  jz      loc_1800072B0
0x18009ee8e  lea     rax, [rsp+0A8h+var_40]
0x18009ee93  mov     [rsp+0A8h+var_80], esi; dwFlags
0x18009ee97  mov     r9d, 4; cbOutput
0x18009ee9d  mov     [rsp+0A8h+var_88], rax; pcbResult
0x18009eea2  lea     r8, [rsp+0A8h+var_48]; pbOutput
0x18009eea7  mov     rcx, rdi; hObject
0x18009eeaa  lea     rdx, aKeystrength; "KeyStrength"
0x18009eeb1  call    BCryptGetProperty
0x18009eeb6  mov     ebx, eax
0x18009eeb8  test    eax, eax
0x18009eeba  jns     short loc_18009EEC9
0x18009eebc  mov     r9d, 0F80h
0x18009eec2  mov     ecx, eax
0x18009eec4  jmp     loc_180007257
0x18009eec9  mov     eax, dword ptr [rsp+0A8h+var_48]
0x18009eecd  mov     r10d, [rsp+0A8h+arg_10]
0x18009eed5  add     eax, 7
0x18009eed8  mov     r11, [rsp+0A8h+arg_8]
0x18009eee0  shr     eax, 3
0x18009eee3  mov     dword ptr [rsp+0A8h+var_48], eax
0x18009eee7  mov     eax, [rsp+0A8h+var_44]
0x18009eeeb  test    eax, eax
0x18009eeed  jz      loc_1800072B0
0x18009eef3  test    r15, r15
0x18009eef6  jnz     short loc_18009EF4F
0x18009eef8  mov     ecx, [rsp+0A8h+cbIV]
0x18009eeff  xor     r9d, r9d
0x18009ef02  mov     dword ptr [rsp+0A8h+var_60], esi
0x18009ef06  mov     r8d, r10d
0x18009ef09  mov     [rsp+0A8h+var_68], rbp
0x18009ef0e  mov     rdx, r11
0x18009ef11  mov     dword ptr [rsp+0A8h+var_70], r12d
0x18009ef16  mov     rax, r14
0x18009ef19  mov     [rsp+0A8h+var_78], rsi
0x18009ef1e  mov     [rsp+0A8h+var_80], ecx
0x18009ef22  mov     rcx, [rsp+0A8h+pbIV]
0x18009ef2a  mov     [rsp+0A8h+var_88], rcx
0x18009ef2f  mov     rcx, [rdi+10h]
0x18009ef33  call    _guard_dispatch_icall
0x18009ef38  mov     ebx, eax
0x18009ef3a  test    eax, eax
0x18009ef3c  jns     loc_180007300
0x18009ef42  mov     r9d, 0F9Eh
0x18009ef48  mov     ecx, eax
0x18009ef4a  jmp     loc_180007257
0x18009ef4f  mov     ecx, dword ptr [rsp+0A8h+var_48]
0x18009ef53  call    MSCryptAlloc
0x18009ef58  mov     rsi, rax
0x18009ef5b  test    rax, rax
0x18009ef5e  jnz     short loc_18009EF75
0x18009ef60  mov     ebx, 0C0000017h
0x18009ef65  mov     r9d, 0FAEh
0x18009ef6b  mov     ecx, 0C0000017h
0x18009ef70  jmp     loc_180007257
0x18009ef75  mov     eax, dword ptr [rsp+0A8h+var_48]
0x18009ef79  mov     ecx, r13d
0x18009ef7c  mov     r9d, [rsp+0A8h+arg_10]
0x18009ef84  mov     r8, [rsp+0A8h+arg_8]
0x18009ef8c  mov     rdx, [rsp+0A8h+arg_18]
0x18009ef94  mov     [rsp+0A8h+var_80], eax
0x18009ef98  mov     [rsp+0A8h+var_88], rsi
0x18009ef9d  call    ApplyEncryptionPadding
0x18009efa2  mov     ebx, eax
0x18009efa4  test    eax, eax
0x18009efa6  jns     short loc_18009EFD1
0x18009efa8  mov     r9d, 0FBBh
0x18009efae  jmp     short loc_18009EFB6
0x18009efb0  mov     r9d, 0FCBh
0x18009efb6  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18009efbd  mov     ecx, eax
0x18009efbf  lea     rdx, aStatus; "Status"
0x18009efc6  call    DebugTraceError
0x18009efcb  nop
0x18009efcc  jmp     loc_180007428
0x18009efd1  mov     eax, [rsp+0A8h+cbIV]
0x18009efd8  xor     r9d, r9d
0x18009efdb  mov     rcx, [rdi+10h]
0x18009efdf  mov     r8d, r12d
0x18009efe2  mov     dword ptr [rsp+0A8h+var_60], 0
0x18009efea  mov     rdx, rsi
0x18009efed  mov     [rsp+0A8h+var_68], rbp
0x18009eff2  mov     dword ptr [rsp+0A8h+var_70], r12d
0x18009eff7  mov     [rsp+0A8h+var_78], r15
0x18009effc  mov     [rsp+0A8h+var_80], eax
0x18009f000  mov     rax, [rsp+0A8h+pbIV]
0x18009f008  mov     [rsp+0A8h+var_88], rax
0x18009f00d  mov     rax, r14
0x18009f010  call    _guard_dispatch_icall
0x18009f015  mov     ebx, eax
0x18009f017  test    eax, eax
0x18009f019  jns     loc_180007300
0x18009f01f  jmp     short loc_18009EFB0
```
