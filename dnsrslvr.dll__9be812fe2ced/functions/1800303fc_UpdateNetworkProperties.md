# UpdateNetworkProperties

- ea: `0x1800303fc`
- end: `0x180030645`
- name: `UpdateNetworkProperties`
- size: `585`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180039350`

## callees

- `0x1800303fc`
- `0x18003064c`
- `0x180046ec0`
- `0x180047818`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `DNSAPI!NetInfo_CreatePerNetworkNetinfo` at `0x1800305d4`
- `DNSAPI!NetInfo_CreatePerNetworkNetinfo` at `0x1800305d4`
- `DNSAPI!NetInfo_Free` at `0x1800305c0`
- `DNSAPI!NetInfo_Free` at `0x1800305c0`
- `DNSAPI!NetInfo_UpdateNetworkProperties` at `0x180030526`
- `DNSAPI!NetInfo_UpdateNetworkProperties` at `0x180030526`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030547`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030547`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800304ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800304ef`
- `NSI!NsiGetAllParameters` at `0x1800304da`
- `NSI!NsiGetAllParameters` at `0x1800304da`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180030461`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180030461`

## pseudocode

```c
unsigned int __fastcall UpdateNetworkProperties(int a1, const NET_LUID *a2)
{
  unsigned int result; // eax
  const NPI_MODULEID *v5; // rdx
  unsigned int updated; // eax
  __int64 v7; // rdx
  __int64 v8; // r9
  ULONG InterfaceIndex; // [rsp+60h] [rbp-A0h] BYREF
  int v10; // [rsp+64h] [rbp-9Ch] BYREF
  NET_LUID v11; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v12[16]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v13; // [rsp+80h] [rbp-80h]
  unsigned int v14; // [rsp+12Ch] [rbp+2Ch]
  _BYTE v15[48]; // [rsp+130h] [rbp+30h] BYREF

  result = (unsigned int)memset_0(v12, 0, 0xF0u);
  InterfaceIndex = 0;
  v10 = 0;
  if ( a2 )
  {
    v11.Value = a2->Value;
    result = ConvertInterfaceLuidToIndex(a2, &InterfaceIndex);
    if ( result )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        return result;
      v8 = InterfaceIndex;
      v7 = 14;
    }
    else
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_d(1035, 15, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, InterfaceIndex);
      v5 = &NPI_MS_IPV6_MODULEID;
      if ( !a1 )
        v5 = &NPI_MS_IPV4_MODULEID;
      result = NsiGetAllParameters(1, v5, 7, &v11, 8, v12, 240, 0, 0, 0, 0);
      if ( !result )
      {
        EnterCriticalSection(&g_csNetinfo);
        updated = NetInfo_UpdateNetworkProperties(
                    InterfaceIndex,
                    v14,
                    v13,
                    v15,
                    g_NetworkInfo,
                    g_PerNetworkNetInfo,
                    &v10);
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_d(1035, 17, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, updated);
        if ( v10 )
        {
          if ( g_PerNetworkNetInfo )
          {
            NetInfo_Free(g_PerNetworkNetInfo);
            NetInfo_CreatePerNetworkNetinfo(g_NetworkInfo, &g_PerNetworkNetInfo);
          }
        }
        LeaveCriticalSection(&g_csNetinfo);
        return Hijack_Start(InterfaceIndex, v15);
      }
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        return result;
      v7 = 16;
      v8 = result;
    }
    return WPP_SF_d(1035, v7, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, v8);
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    return WPP_SF_(1035, 13, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1800303fc  mov     [rsp-8+arg_0], rbx
0x180030401  mov     [rsp-8+arg_10], rdi
0x180030406  push    rbp
0x180030407  lea     rbp, [rsp-70h]
0x18003040c  sub     rsp, 170h
0x180030413  mov     rax, cs:__security_cookie
0x18003041a  xor     rax, rsp
0x18003041d  mov     [rbp+70h+var_10], rax
0x180030421  mov     rbx, rdx
0x180030424  mov     edi, ecx
0x180030426  xor     edx, edx; Val
0x180030428  lea     rcx, [rsp+170h+var_100]; void *
0x18003042d  mov     r8d, 0F0h; Size
0x180030433  call    memset_0
0x180030438  mov     [rsp+170h+InterfaceIndex], 0
0x180030440  mov     [rsp+170h+var_10C], 0
0x180030448  test    rbx, rbx
0x18003044b  jz      loc_1800305DF
0x180030451  mov     rax, [rbx]
0x180030454  lea     rdx, [rsp+170h+InterfaceIndex]; InterfaceIndex
0x180030459  mov     rcx, rbx; InterfaceLuid
0x18003045c  mov     [rsp+170h+var_108], rax
0x180030461  call    cs:__imp_ConvertInterfaceLuidToIndex
0x180030467  test    eax, eax
0x180030469  jnz     loc_18003059F
0x18003046f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180030476  jnz     loc_180030607
0x18003047c  mov     [rsp+170h+var_120], 0
0x180030484  lea     rax, NPI_MS_IPV4_MODULEID
0x18003048b  mov     [rsp+170h+var_128], 0
0x180030494  lea     rdx, NPI_MS_IPV6_MODULEID
0x18003049b  mov     [rsp+170h+var_130], 0
0x1800304a3  lea     r9, [rsp+170h+var_108]
0x1800304a8  mov     [rsp+170h+var_138], 0
0x1800304b1  mov     ecx, 1
0x1800304b6  mov     dword ptr [rsp+170h+var_140], 0F0h
0x1800304be  test    edi, edi
0x1800304c0  cmovz   rdx, rax
0x1800304c4  lea     rax, [rsp+170h+var_100]
0x1800304c9  mov     [rsp+170h+var_148], rax
0x1800304ce  lea     r8d, [rcx+6]
0x1800304d2  mov     dword ptr [rsp+170h+var_150], 8
0x1800304da  call    cs:__imp_NsiGetAllParameters
0x1800304e0  test    eax, eax
0x1800304e2  jnz     loc_18003057B
0x1800304e8  lea     rcx, g_csNetinfo; lpCriticalSection
0x1800304ef  call    cs:__imp_EnterCriticalSection
0x1800304f5  mov     r8d, [rbp+70h+var_F0]
0x1800304f9  lea     rax, [rsp+170h+var_10C]
0x1800304fe  mov     edx, [rbp+70h+var_44]
0x180030501  lea     r9, [rbp+70h+var_40]
0x180030505  mov     ecx, [rsp+170h+InterfaceIndex]
0x180030509  mov     [rsp+170h+var_140], rax
0x18003050e  mov     rax, cs:g_PerNetworkNetInfo
0x180030515  mov     [rsp+170h+var_148], rax
0x18003051a  mov     rax, cs:g_NetworkInfo
0x180030521  mov     [rsp+170h+var_150], rax
0x180030526  call    cs:__imp_NetInfo_UpdateNetworkProperties
0x18003052c  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180030533  jnz     loc_180030627
0x180030539  cmp     [rsp+170h+var_10C], 0
0x18003053e  jnz     short loc_1800305B4
0x180030540  lea     rcx, g_csNetinfo; lpCriticalSection
0x180030547  call    cs:__imp_LeaveCriticalSection
0x18003054d  mov     ecx, [rsp+170h+InterfaceIndex]
0x180030551  lea     rdx, [rbp+70h+var_40]
0x180030555  call    Hijack_Start
0x18003055a  mov     rcx, [rbp+70h+var_10]
0x18003055e  xor     rcx, rsp; StackCookie
0x180030561  call    __security_check_cookie
0x180030566  lea     r11, [rsp+170h+var_s0]
0x18003056e  mov     rbx, [r11+10h]
0x180030572  mov     rdi, [r11+20h]
0x180030576  mov     rsp, r11
0x180030579  pop     rbp
0x18003057a  retn
0x18003057b  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180030582  jz      short loc_18003055A
0x180030584  mov     edx, 10h
0x180030589  mov     r9d, eax
0x18003058c  mov     ecx, 40Bh
0x180030591  lea     r8, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids
0x180030598  call    WPP_SF_d
0x18003059d  jmp     short loc_18003055A
0x18003059f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800305a6  jz      short loc_18003055A
0x1800305a8  mov     r9d, [rsp+170h+InterfaceIndex]
0x1800305ad  mov     edx, 0Eh
0x1800305b2  jmp     short loc_18003058C
0x1800305b4  mov     rcx, cs:g_PerNetworkNetInfo
0x1800305bb  test    rcx, rcx
0x1800305be  jz      short loc_180030540
0x1800305c0  call    cs:__imp_NetInfo_Free
0x1800305c6  mov     rcx, cs:g_NetworkInfo
0x1800305cd  lea     rdx, g_PerNetworkNetInfo
0x1800305d4  call    cs:__imp_NetInfo_CreatePerNetworkNetinfo
0x1800305da  jmp     loc_180030540
0x1800305df  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800305e6  jz      loc_18003055A
0x1800305ec  mov     edx, 0Dh
0x1800305f1  lea     r8, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids
0x1800305f8  mov     ecx, 40Bh
0x1800305fd  call    WPP_SF_
0x180030602  jmp     loc_18003055A
0x180030607  mov     r9d, [rsp+170h+InterfaceIndex]
0x18003060c  lea     r8, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids
0x180030613  mov     edx, 0Fh
0x180030618  mov     ecx, 40Bh
0x18003061d  call    WPP_SF_d
0x180030622  jmp     loc_18003047C
0x180030627  mov     edx, 11h
0x18003062c  lea     r8, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids
0x180030633  mov     ecx, 40Bh
0x180030638  mov     r9d, eax
0x18003063b  call    WPP_SF_d
0x180030640  jmp     loc_180030539
```
