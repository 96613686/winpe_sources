# DDMAdminUpdateQoSPolicies

- ea: `0x180007400`
- end: `0x18000756b`
- name: `DDMAdminUpdateQoSPolicies`
- size: `363`
- prototype: `__int64 __fastcall(LPVOID lpInBuffer)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007400`
- `0x180007c0c`
- `0x180014c9c`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `rasman!RasUpdateQoSPolicies` at `0x1800074ae`
- `rasman!RasUpdateQoSPolicies` at `0x1800074ae`

## string_xrefs

- `0x180007475`: `DDMAdminUpdateQoSPolicies`
- `0x1800074d5`: `DDMAdminUpdateQoSPolicies`
- `0x18000747c`: `%s: DdmUpdateQoSPolicies failed: %d`
- `0x1800074dc`: `%s: RasUpdateQoSPolicies failed: %d`

## pseudocode

```c
__int64 __fastcall DDMAdminUpdateQoSPolicies(LPVOID lpInBuffer)
{
  unsigned int updated; // eax
  unsigned int v3; // ebx
  __int64 v4; // r8
  __int64 v5; // rax
  unsigned int v6; // eax
  _BYTE v8[16]; // [rsp+30h] [rbp-D0h] BYREF
  int *v9; // [rsp+40h] [rbp-C0h]
  int v10; // [rsp+48h] [rbp-B8h]
  int v11; // [rsp+4Ch] [rbp-B4h]
  int v12; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v13[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v12 = 0;
  memset_0(v13, 0, sizeof(v13));
  if ( dword_1800CF654 )
  {
    updated = DdmUpdateQoSPolicies(lpInBuffer);
    v3 = updated;
    if ( updated )
    {
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v12) = 0;
        FormatRRASErrorString(&v12, L"%s: DdmUpdateQoSPolicies failed: %d", L"DDMAdminUpdateQoSPolicies", updated);
        if ( (byte_1800CF404 & 8) != 0 )
        {
          v5 = -1;
          do
            ++v5;
          while ( *(_WORD *)&v13[2 * v5 - 4] );
LABEL_13:
          v11 = 0;
          v10 = 2 * v5 + 2;
          v9 = &v12;
          McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v4, 2, v8);
        }
      }
    }
  }
  else
  {
    v6 = RasUpdateQoSPolicies(lpInBuffer);
    v3 = v6;
    if ( v6 )
    {
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v12) = 0;
        FormatRRASErrorString(&v12, L"%s: RasUpdateQoSPolicies failed: %d", L"DDMAdminUpdateQoSPolicies", v6);
        if ( (byte_1800CF404 & 8) != 0 )
        {
          v5 = -1;
          do
            ++v5;
          while ( *(_WORD *)&v13[2 * v5 - 4] );
          goto LABEL_13;
        }
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180007400  mov     [rsp-8+arg_8], rbx
0x180007405  mov     [rsp-8+arg_10], rdi
0x18000740a  push    rbp
0x18000740b  lea     rbp, [rsp-760h]
0x180007413  sub     rsp, 860h
0x18000741a  mov     rax, cs:__security_cookie
0x180007421  xor     rax, rsp
0x180007424  mov     [rbp+760h+var_10], rax
0x18000742b  mov     rbx, rcx
0x18000742e  xor     edi, edi
0x180007430  lea     rcx, [rsp+860h+var_80C]; void *
0x180007435  mov     [rsp+860h+var_810], edi
0x180007439  xor     edx, edx; Val
0x18000743b  mov     r8d, 7FCh; Size
0x180007441  call    memset_0
0x180007446  cmp     cs:dword_1800CF654, edi
0x18000744c  mov     rcx, rbx; lpInBuffer
0x18000744f  jz      short loc_1800074AE
0x180007451  call    DdmUpdateQoSPolicies
0x180007456  mov     ebx, eax
0x180007458  test    eax, eax
0x18000745a  jz      loc_180007544
0x180007460  test    cs:byte_1800CF404, 8
0x180007467  jz      loc_180007544
0x18000746d  mov     r9d, eax
0x180007470  mov     word ptr [rsp+860h+var_810], di
0x180007475  lea     r8, aDdmadminupdate_1; "DDMAdminUpdateQoSPolicies"
0x18000747c  lea     rdx, aSDdmupdateqosp; "%s: DdmUpdateQoSPolicies failed: %d"
0x180007483  lea     rcx, [rsp+860h+var_810]
0x180007488  call    FormatRRASErrorString
0x18000748d  test    cs:byte_1800CF404, 8
0x180007494  jz      loc_180007544
0x18000749a  lea     rcx, [rsp+860h+var_810]
0x18000749f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800074a3  inc     rax
0x1800074a6  cmp     [rcx+rax*2], di
0x1800074aa  jnz     short loc_1800074A3
0x1800074ac  jmp     short loc_180007508
0x1800074ae  call    cs:__imp_RasUpdateQoSPolicies
0x1800074b5  nop     dword ptr [rax+rax+00h]
0x1800074ba  mov     ebx, eax
0x1800074bc  test    eax, eax
0x1800074be  jz      loc_180007544
0x1800074c4  test    cs:byte_1800CF404, 8
0x1800074cb  jz      short loc_180007544
0x1800074cd  mov     r9d, eax
0x1800074d0  mov     word ptr [rsp+860h+var_810], di
0x1800074d5  lea     r8, aDdmadminupdate_1; "DDMAdminUpdateQoSPolicies"
0x1800074dc  lea     rdx, aSRasupdateqosp; "%s: RasUpdateQoSPolicies failed: %d"
0x1800074e3  lea     rcx, [rsp+860h+var_810]
0x1800074e8  call    FormatRRASErrorString
0x1800074ed  test    cs:byte_1800CF404, 8
0x1800074f4  jz      short loc_180007544
0x1800074f6  lea     rcx, [rsp+860h+var_810]
0x1800074fb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800074ff  inc     rax
0x180007502  cmp     [rcx+rax*2], di
0x180007506  jnz     short loc_1800074FF
0x180007508  lea     eax, ds:2[rax*2]
0x18000750f  mov     [rsp+860h+var_814], edi
0x180007513  lea     rcx, [rsp+860h+var_810]
0x180007518  mov     [rsp+860h+var_818], eax
0x18000751c  lea     rax, [rsp+860h+var_830]
0x180007521  mov     [rsp+860h+var_820], rcx
0x180007526  mov     r9d, 2
0x18000752c  mov     [rsp+860h+var_840], rax
0x180007531  lea     rdx, RasDdmTraceError
0x180007538  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000753f  call    McGenEventWrite_EventWriteTransfer
0x180007544  mov     eax, ebx
0x180007546  mov     rcx, [rbp+760h+var_10]
0x18000754d  xor     rcx, rsp; StackCookie
0x180007550  call    __security_check_cookie
0x180007555  lea     r11, [rsp+860h+var_s0]
0x18000755d  mov     rbx, [r11+18h]
0x180007561  mov     rdi, [r11+20h]
0x180007565  mov     rsp, r11
0x180007568  pop     rbp
0x180007569  retn
```
