# BthServPushPolicies(void)

- ea: `0x18001dd58`
- end: `0x18001e020`
- name: `?BthServPushPolicies@@YAXXZ`
- size: `712`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180010f60`
- `0x18001e8a0`

## callees

- `0x180012004`
- `0x1800120b8`
- `0x18001dd58`
- `0x18001e1dc`
- `0x1800320ac`
- `0x180032b34`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001dde0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001dde0`
- `ntdll!RtlPublishWnfStateData` at `0x18001dfb0`
- `ntdll!RtlPublishWnfStateData` at `0x18001dfb0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ddba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ddba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001df1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001df1a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void BthServPushPolicies(void)
{
  int v0; // edx
  int v1; // r8d
  int PolicyRegistryLocation; // ebx
  LSTATUS v3; // eax
  int v4; // ebx
  int v5; // edx
  int v6; // r8d
  char v7; // di
  bool v8; // dl
  _QWORD *v9; // rcx
  int v10; // edx
  int v11; // r8d
  LPCWSTR lpSubKey[2]; // [rsp+50h] [rbp-28h] BYREF
  int v13; // [rsp+80h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+10h] BYREF

  if ( (int)BthSyncWithPolicyManager() >= 0 )
  {
    hKey = 0;
    *(_OWORD *)lpSubKey = 0;
    PolicyRegistryLocation = BthGetPolicyRegistryLocation((PUNICODE_STRING)lpSubKey);
    if ( PolicyRegistryLocation < 0 )
    {
      v4 = PolicyRegistryLocation | 0x10000000;
    }
    else
    {
      v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[1], 0, 0x20006u, &hKey);
      v4 = v3;
      if ( v3 > 0 )
        v4 = (unsigned __int16)v3 | 0x80070000;
    }
    free((void *)lpSubKey[1]);
    if ( v4 < 0 )
    {
      v7 = 1;
      v9 = WPP_GLOBAL_Control;
      LOBYTE(v5) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !(_BYTE)v5 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_29:
        if ( hKey )
          RegCloseKey(hKey);
        goto LABEL_38;
      }
    }
    else
    {
      v7 = 1;
      v8 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
      if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v8,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      if ( (int)BthServReplicatePolicies(hKey) >= 0 )
        goto LABEL_29;
      v9 = WPP_GLOBAL_Control;
      LOBYTE(v5) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !(_BYTE)v5 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_29;
    }
    WPP_RECORDER_AND_TRACE_SF_sD(v9[2], v5, v6, v9[5]);
    goto LABEL_29;
  }
  v7 = 1;
  LOBYTE(v0) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
  if ( (_BYTE)v0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v1) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v0, v1, *((_QWORD *)WPP_GLOBAL_Control + 5));
  }
LABEL_38:
  v13 = 1;
  if ( (int)RtlPublishWnfStateData(WNF_ENTR_BLUETOOTH_POLICY_VALUE_CHANGED, 0, &v13, 4, 0) < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v7 = 0;
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = v7;
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
  }
}

```

## disassembly

```asm
0x18001dd58  mov     [rsp+arg_10], rbx
0x18001dd5d  mov     [rsp+arg_18], rbp
0x18001dd62  push    rsi
0x18001dd63  push    rdi
0x18001dd64  push    r14
0x18001dd66  sub     rsp, 60h
0x18001dd6a  call    BthSyncWithPolicyManager
0x18001dd6f  test    eax, eax
0x18001dd71  js      loc_18001DF28
0x18001dd77  and     [rsp+78h+hKey], 0
0x18001dd80  xorps   xmm0, xmm0
0x18001dd83  movups  xmmword ptr [rsp+78h+lpSubKey], xmm0
0x18001dd88  lea     rcx, [rsp+78h+lpSubKey]; DestinationString
0x18001dd8d  call    BthGetPolicyRegistryLocation
0x18001dd92  mov     ebx, eax
0x18001dd94  test    eax, eax
0x18001dd96  js      short loc_18001DDD7
0x18001dd98  lea     rax, [rsp+78h+hKey]
0x18001dda0  mov     [rsp+78h+phkResult], rax; phkResult
0x18001dda5  mov     r9d, 20006h; samDesired
0x18001ddab  xor     r8d, r8d; ulOptions
0x18001ddae  mov     rdx, [rsp+78h+lpSubKey+8]; lpSubKey
0x18001ddb3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ddba  call    cs:__imp_RegOpenKeyExW
0x18001ddc1  nop     dword ptr [rax+rax+00h]
0x18001ddc6  mov     ebx, eax
0x18001ddc8  test    eax, eax
0x18001ddca  jle     short loc_18001DDDB
0x18001ddcc  movzx   ebx, ax
0x18001ddcf  or      ebx, 80070000h
0x18001ddd5  jmp     short loc_18001DDDB
0x18001ddd7  bts     ebx, 1Ch
0x18001dddb  mov     rcx, [rsp+78h+lpSubKey+8]; Block
0x18001dde0  call    cs:__imp_free
0x18001dde7  nop     dword ptr [rax+rax+00h]
0x18001ddec  test    ebx, ebx
0x18001ddee  js      loc_18001DEA8
0x18001ddf4  lea     rsi, WPP_GLOBAL_Control
0x18001ddfb  mov     edi, 1
0x18001de00  mov     rcx, cs:WPP_GLOBAL_Control
0x18001de07  cmp     rcx, rsi
0x18001de0a  jz      short loc_18001DE17
0x18001de0c  cmp     byte ptr [rcx+19h], 4
0x18001de10  jb      short loc_18001DE17
0x18001de12  mov     dl, dil
0x18001de15  jmp     short loc_18001DE19
0x18001de17  xor     dl, dl
0x18001de19  lea     rbp, WPP_RECORDER_INITIALIZED
0x18001de20  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001de27  setnz   r8b
0x18001de2b  lea     r14, WPP_1ad68b0ce8773238920c85c6e45f2d1d_Traceguids
0x18001de32  test    dl, dl
0x18001de34  jnz     short loc_18001DE3B
0x18001de36  test    r8b, r8b
0x18001de39  jz      short loc_18001DE54
0x18001de3b  mov     [rsp+78h+var_40], r14
0x18001de40  mov     [rsp+78h+var_48], 15h
0x18001de47  mov     r9, [rcx+28h]
0x18001de4b  mov     rcx, [rcx+10h]
0x18001de4f  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001de54  mov     rcx, [rsp+78h+hKey]; hKey
0x18001de5c  call    BthServReplicatePolicies
0x18001de61  test    eax, eax
0x18001de63  jns     loc_18001DF0D
0x18001de69  mov     rcx, cs:WPP_GLOBAL_Control
0x18001de70  cmp     rcx, rsi
0x18001de73  jz      short loc_18001DE80
0x18001de75  cmp     byte ptr [rcx+19h], 2
0x18001de79  jb      short loc_18001DE80
0x18001de7b  mov     dl, dil
0x18001de7e  jmp     short loc_18001DE82
0x18001de80  xor     dl, dl
0x18001de82  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001de89  setnz   r8b
0x18001de8d  test    dl, dl
0x18001de8f  jnz     short loc_18001DE96
0x18001de91  test    r8b, r8b
0x18001de94  jz      short loc_18001DF0D
0x18001de96  mov     [rsp+78h+var_30], eax
0x18001de9a  mov     [rsp+78h+var_40], r14
0x18001de9f  mov     [rsp+78h+var_48], 16h
0x18001dea6  jmp     short loc_18001DEFF
0x18001dea8  lea     rsi, WPP_GLOBAL_Control
0x18001deaf  mov     edi, 1
0x18001deb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001debb  cmp     rcx, rsi
0x18001debe  jz      short loc_18001DECB
0x18001dec0  cmp     byte ptr [rcx+19h], 2
0x18001dec4  jb      short loc_18001DECB
0x18001dec6  mov     dl, dil
0x18001dec9  jmp     short loc_18001DECD
0x18001decb  xor     dl, dl
0x18001decd  lea     rbp, WPP_RECORDER_INITIALIZED
0x18001ded4  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001dedb  setnz   r8b
0x18001dedf  lea     r14, WPP_1ad68b0ce8773238920c85c6e45f2d1d_Traceguids
0x18001dee6  test    dl, dl
0x18001dee8  jnz     short loc_18001DEEF
0x18001deea  test    r8b, r8b
0x18001deed  jz      short loc_18001DF0D
0x18001deef  mov     [rsp+78h+var_30], ebx
0x18001def3  mov     [rsp+78h+var_40], r14
0x18001def8  mov     [rsp+78h+var_48], 17h
0x18001deff  mov     r9, [rcx+28h]
0x18001df03  mov     rcx, [rcx+10h]
0x18001df07  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18001df0c  nop
0x18001df0d  mov     rcx, [rsp+78h+hKey]; hKey
0x18001df15  test    rcx, rcx
0x18001df18  jz      short loc_18001DF8C
0x18001df1a  call    cs:__imp_RegCloseKey
0x18001df21  nop     dword ptr [rax+rax+00h]
0x18001df26  jmp     short loc_18001DF8C
0x18001df28  lea     rsi, WPP_GLOBAL_Control
0x18001df2f  mov     edi, 1
0x18001df34  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df3b  cmp     rcx, rsi
0x18001df3e  jz      short loc_18001DF4B
0x18001df40  cmp     byte ptr [rcx+19h], 2
0x18001df44  jb      short loc_18001DF4B
0x18001df46  mov     dl, dil
0x18001df49  jmp     short loc_18001DF4D
0x18001df4b  xor     dl, dl
0x18001df4d  lea     rbp, WPP_RECORDER_INITIALIZED
0x18001df54  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001df5b  setnz   r8b
0x18001df5f  lea     r14, WPP_1ad68b0ce8773238920c85c6e45f2d1d_Traceguids
0x18001df66  test    dl, dl
0x18001df68  jnz     short loc_18001DF6F
0x18001df6a  test    r8b, r8b
0x18001df6d  jz      short loc_18001DF8C
0x18001df6f  mov     [rsp+78h+var_30], eax
0x18001df73  mov     [rsp+78h+var_40], r14
0x18001df78  mov     [rsp+78h+var_48], 18h
0x18001df7f  mov     r9, [rcx+28h]
0x18001df83  mov     rcx, [rcx+10h]
0x18001df87  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18001df8c  mov     [rsp+78h+arg_0], edi
0x18001df93  and     [rsp+78h+phkResult], 0
0x18001df99  mov     r9d, 4
0x18001df9f  lea     r8, [rsp+78h+arg_0]
0x18001dfa7  xor     edx, edx
0x18001dfa9  mov     rcx, cs:WNF_ENTR_BLUETOOTH_POLICY_VALUE_CHANGED
0x18001dfb0  call    cs:__imp_RtlPublishWnfStateData
0x18001dfb7  nop     dword ptr [rax+rax+00h]
0x18001dfbc  test    eax, eax
0x18001dfbe  jns     short loc_18001E00A
0x18001dfc0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dfc7  cmp     rcx, rsi
0x18001dfca  jz      short loc_18001DFD2
0x18001dfcc  cmp     byte ptr [rcx+19h], 2
0x18001dfd0  jnb     short loc_18001DFD5
0x18001dfd2  xor     dil, dil
0x18001dfd5  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001dfdc  setnz   r8b
0x18001dfe0  test    dil, dil
0x18001dfe3  jnz     short loc_18001DFEA
0x18001dfe5  test    r8b, r8b
0x18001dfe8  jz      short loc_18001E00A
0x18001dfea  mov     [rsp+78h+var_30], eax
0x18001dfee  mov     [rsp+78h+var_40], r14
0x18001dff3  mov     [rsp+78h+var_48], 19h
0x18001dffa  mov     r9, [rcx+28h]
0x18001dffe  mov     dl, dil
0x18001e001  mov     rcx, [rcx+10h]
0x18001e005  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18001e00a  lea     r11, [rsp+78h+var_18]
0x18001e00f  mov     rbx, [r11+30h]
0x18001e013  mov     rbp, [r11+38h]
0x18001e017  mov     rsp, r11
0x18001e01a  pop     r14
0x18001e01c  pop     rdi
0x18001e01d  pop     rsi
0x18001e01e  retn
```
