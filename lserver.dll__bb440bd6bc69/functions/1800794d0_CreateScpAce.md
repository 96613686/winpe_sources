# CreateScpAce

- ea: `0x1800794d0`
- end: `0x180079739`
- name: `CreateScpAce`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180079104`

## callees

- `0x18001aea4`
- `0x1800794d0`
- `0x1800a5010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180079509`
- `ole32!CoCreateInstance` at `0x180079509`
- `OLEAUT32!__imp_SysFreeString` at `0x180079714`
- `OLEAUT32!__imp_SysFreeString` at `0x180079714`

## string_xrefs

- `0x180079541`: `"Create ACE for SCP"`
- `0x18007958d`: `"(*ppAce)->put_AccessMask"`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CreateScpAce(LPVOID *a1, BSTR *a2, __int64 a3)
{
  HRESULT Instance; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  int v9; // edx
  const wchar_t *v10; // r9

  Instance = CoCreateInstance(&CLSID_AccessControlEntry, 0, 1u, &IID_IADsAccessControlEntry, a1);
  v7 = Instance;
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)*a1 + 64LL))(*a1, 48);
    v7 = Instance;
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)*a1 + 160LL))(*a1, *a2);
      v7 = Instance;
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)*a1 + 80LL))(*a1, 5);
        v7 = Instance;
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)*a1 + 96LL))(*a1, 0);
          v7 = Instance;
          if ( Instance >= 0 )
          {
            Instance = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)*a1 + 112LL))(*a1, 1);
            v7 = Instance;
            if ( Instance >= 0 )
            {
              Instance = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)*a1 + 128LL))(*a1, a3);
              v7 = Instance;
              if ( Instance < 0 )
              {
                v8 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v9 = 71;
                  v10 = L"\"(*ppAce)->put_ObjectType\"";
                  goto LABEL_29;
                }
              }
            }
            else
            {
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v9 = 70;
                v10 = L"\"(*ppAce)->put_Flags\"";
                goto LABEL_29;
              }
            }
          }
          else
          {
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v9 = 69;
              v10 = L"\"(*ppAce)->put_AceFlags\"";
              goto LABEL_29;
            }
          }
        }
        else
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v9 = 68;
            v10 = L"\"(*ppAce)->put_AceType\"";
            goto LABEL_29;
          }
        }
      }
      else
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = 67;
          v10 = L"\"(*ppAce)->put_Trustee\"";
          goto LABEL_29;
        }
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 66;
        v10 = L"\"(*ppAce)->put_AccessMask\"";
        goto LABEL_29;
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 65;
      v10 = L"\"Create ACE for SCP\"";
LABEL_29:
      WPP_SF_SD(v8[2], v9, (unsigned int)WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids, (_DWORD)v10, Instance);
    }
  }
  SysFreeString(*a2);
  return v7;
}

```

## disassembly

```asm
0x1800794d0  mov     rax, rsp
0x1800794d3  mov     [rax+8], rbx
0x1800794d7  mov     [rax+18h], rbp
0x1800794db  mov     [rax+20h], rsi
0x1800794df  mov     [rax+10h], rdx
0x1800794e3  push    rdi
0x1800794e4  sub     rsp, 30h
0x1800794e8  mov     rbp, r8
0x1800794eb  mov     rsi, rdx
0x1800794ee  mov     rdi, rcx
0x1800794f1  mov     [rax-18h], rcx
0x1800794f5  lea     r9, IID_IADsAccessControlEntry; riid
0x1800794fc  xor     edx, edx; pUnkOuter
0x1800794fe  lea     r8d, [rdx+1]; dwClsContext
0x180079502  lea     rcx, CLSID_AccessControlEntry; rclsid
0x180079509  call    cs:__imp_CoCreateInstance
0x180079510  nop     dword ptr [rax+rax+00h]
0x180079515  mov     ebx, eax
0x180079517  test    eax, eax
0x180079519  jns     short loc_18007954D
0x18007951b  lea     rdx, WPP_GLOBAL_Control
0x180079522  mov     rcx, cs:WPP_GLOBAL_Control
0x180079529  cmp     rcx, rdx
0x18007952c  jz      loc_180079711
0x180079532  cmp     byte ptr [rcx+19h], 2
0x180079536  jb      loc_180079711
0x18007953c  mov     edx, 41h ; 'A'
0x180079541  lea     r9, aCreateAceForSc; "\"Create ACE for SCP\""
0x180079548  jmp     loc_1800796FC
0x18007954d  mov     rcx, [rdi]
0x180079550  mov     rax, [rcx]
0x180079553  mov     edx, 30h ; '0'
0x180079558  mov     rax, [rax+40h]
0x18007955c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079561  mov     ebx, eax
0x180079563  test    eax, eax
0x180079565  jns     short loc_180079599
0x180079567  lea     rdx, WPP_GLOBAL_Control
0x18007956e  mov     rcx, cs:WPP_GLOBAL_Control
0x180079575  cmp     rcx, rdx
0x180079578  jz      loc_180079711
0x18007957e  cmp     byte ptr [rcx+19h], 2
0x180079582  jb      loc_180079711
0x180079588  mov     edx, 42h ; 'B'
0x18007958d  lea     r9, aPpacePutAccess; "\"(*ppAce)->put_AccessMask\""
0x180079594  jmp     loc_1800796FC
0x180079599  mov     rcx, [rdi]
0x18007959c  mov     rax, [rcx]
0x18007959f  mov     rdx, [rsi]
0x1800795a2  mov     rax, [rax+0A0h]
0x1800795a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800795ae  mov     ebx, eax
0x1800795b0  test    eax, eax
0x1800795b2  jns     short loc_1800795E6
0x1800795b4  lea     rdx, WPP_GLOBAL_Control
0x1800795bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800795c2  cmp     rcx, rdx
0x1800795c5  jz      loc_180079711
0x1800795cb  cmp     byte ptr [rcx+19h], 2
0x1800795cf  jb      loc_180079711
0x1800795d5  mov     edx, 43h ; 'C'
0x1800795da  lea     r9, aPpacePutTruste; "\"(*ppAce)->put_Trustee\""
0x1800795e1  jmp     loc_1800796FC
0x1800795e6  mov     rcx, [rdi]
0x1800795e9  mov     rax, [rcx]
0x1800795ec  mov     edx, 5
0x1800795f1  mov     rax, [rax+50h]
0x1800795f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800795fa  mov     ebx, eax
0x1800795fc  test    eax, eax
0x1800795fe  jns     short loc_180079632
0x180079600  lea     rdx, WPP_GLOBAL_Control
0x180079607  mov     rcx, cs:WPP_GLOBAL_Control
0x18007960e  cmp     rcx, rdx
0x180079611  jz      loc_180079711
0x180079617  cmp     byte ptr [rcx+19h], 2
0x18007961b  jb      loc_180079711
0x180079621  mov     edx, 44h ; 'D'
0x180079626  lea     r9, aPpacePutAcetyp; "\"(*ppAce)->put_AceType\""
0x18007962d  jmp     loc_1800796FC
0x180079632  mov     rcx, [rdi]
0x180079635  mov     rax, [rcx]
0x180079638  xor     edx, edx
0x18007963a  mov     rax, [rax+60h]
0x18007963e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079643  mov     ebx, eax
0x180079645  test    eax, eax
0x180079647  jns     short loc_18007967B
0x180079649  lea     rdx, WPP_GLOBAL_Control
0x180079650  mov     rcx, cs:WPP_GLOBAL_Control
0x180079657  cmp     rcx, rdx
0x18007965a  jz      loc_180079711
0x180079660  cmp     byte ptr [rcx+19h], 2
0x180079664  jb      loc_180079711
0x18007966a  mov     edx, 45h ; 'E'
0x18007966f  lea     r9, aPpacePutAcefla; "\"(*ppAce)->put_AceFlags\""
0x180079676  jmp     loc_1800796FC
0x18007967b  mov     rcx, [rdi]
0x18007967e  mov     rax, [rcx]
0x180079681  mov     edx, 1
0x180079686  mov     rax, [rax+70h]
0x18007968a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007968f  mov     ebx, eax
0x180079691  test    eax, eax
0x180079693  jns     short loc_1800796BC
0x180079695  lea     rdx, WPP_GLOBAL_Control
0x18007969c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800796a3  cmp     rcx, rdx
0x1800796a6  jz      short loc_180079711
0x1800796a8  cmp     byte ptr [rcx+19h], 2
0x1800796ac  jb      short loc_180079711
0x1800796ae  mov     edx, 46h ; 'F'
0x1800796b3  lea     r9, aPpacePutFlags; "\"(*ppAce)->put_Flags\""
0x1800796ba  jmp     short loc_1800796FC
0x1800796bc  mov     rcx, [rdi]
0x1800796bf  mov     rax, [rcx]
0x1800796c2  mov     rdx, rbp
0x1800796c5  mov     rax, [rax+80h]
0x1800796cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800796d1  mov     ebx, eax
0x1800796d3  test    eax, eax
0x1800796d5  jns     short loc_180079711
0x1800796d7  lea     rdx, WPP_GLOBAL_Control
0x1800796de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800796e5  cmp     rcx, rdx
0x1800796e8  jz      short loc_180079711
0x1800796ea  cmp     byte ptr [rcx+19h], 2
0x1800796ee  jb      short loc_180079711
0x1800796f0  mov     edx, 47h ; 'G'
0x1800796f5  lea     r9, aPpacePutObject; "\"(*ppAce)->put_ObjectType\""
0x1800796fc  mov     [rsp+38h+var_18], eax
0x180079700  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x180079707  mov     rcx, [rcx+10h]
0x18007970b  call    WPP_SF_SD
0x180079710  nop
0x180079711  mov     rcx, [rsi]; bstrString
0x180079714  call    cs:__imp_SysFreeString
0x18007971b  nop     dword ptr [rax+rax+00h]
0x180079720  nop
0x180079721  mov     eax, ebx
0x180079723  mov     rbx, [rsp+38h+arg_0]
0x180079728  mov     rbp, [rsp+38h+arg_10]
0x18007972d  mov     rsi, [rsp+38h+arg_18]
0x180079732  add     rsp, 30h
0x180079736  pop     rdi
0x180079737  retn
```
