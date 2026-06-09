# CRDPENCOMConnectionStringDeserializer::XMLDeserialize(ushort *)

- ea: `0x1800f6440`
- end: `0x1800f6811`
- name: `?XMLDeserialize@CRDPENCOMConnectionStringDeserializer@@UEAAJPEAG@Z`
- size: `977`
- prototype: `int(CRDPENCOMConnectionStringDeserializer *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180046a84`
- `0x1800711c8`
- `0x1800721d4`
- `0x1800f6440`
- `0x18015f52c`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f6472`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f6472`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f653f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f65a9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f6613`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f653f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f65a9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f6613`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f67de`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f67ec`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f67fa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f67de`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f67ec`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f67fa`

## string_xrefs

- `0x1800f64b3`: `Failed to create the XML document`
- `0x1800f660c`: `T[@ID!='' and @SID!='']`
- `0x1800f652f`: `Failed to deserialize the root element`

## pseudocode

```c
__int64 __fastcall CRDPENCOMConnectionStringDeserializer::XMLDeserialize(LPVOID *this, unsigned __int16 *a2)
{
  struct IXMLDOMNode **v2; // rdi
  HRESULT Instance; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v7; // edx
  const char *v8; // rcx
  _QWORD *v9; // r14
  OLECHAR *v10; // r12
  unsigned int v11; // eax
  OLECHAR *v12; // rbp
  OLECHAR *v13; // rdi
  unsigned int v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // eax
  int v17; // edx
  const char *v18; // rcx
  unsigned int v19; // eax
  LPVOID v20; // rcx

  v2 = (struct IXMLDOMNode **)(this + 7);
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60, this + 7);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 32;
      v8 = "Failed to create the XML document";
LABEL_6:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        (unsigned int)WPP_e46c42e76a903292174a4e9de97c4af5_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v8,
        Instance);
      return (unsigned int)Instance;
    }
    return (unsigned int)Instance;
  }
  v9 = this + 8;
  Instance = RDPENCHLPXML_AddElementFromXMLString(*v2, a2, (struct IXMLDOMNode **)this + 8);
  if ( Instance >= 0 )
  {
    v10 = SysAllocString(L"A");
    if ( !v10 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          34,
          WPP_e46c42e76a903292174a4e9de97c4af5_Traceguids,
          v11,
          -2147024882);
      }
      return (unsigned int)-2147024882;
    }
    v12 = SysAllocString(L"C");
    if ( v12 )
    {
      v13 = SysAllocString(L"T[@ID!='' and @SID!='']");
      if ( v13 )
      {
        Instance = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, char *))(*(_QWORD *)*v9 + 296LL))(
                     *v9,
                     v10,
                     (char *)this + 72);
        if ( Instance >= 0 )
        {
          if ( !this[9] )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v19 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                38,
                WPP_e46c42e76a903292174a4e9de97c4af5_Traceguids,
                v19,
                -2147418113);
            }
            Instance = -2147418113;
            goto LABEL_53;
          }
          Instance = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, char *))(*(_QWORD *)*v9 + 296LL))(
                       *v9,
                       v12,
                       (char *)this + 80);
          if ( Instance >= 0 )
          {
            v20 = this[10];
            if ( !v20 )
              goto LABEL_53;
            Instance = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, char *))(*(_QWORD *)v20 + 288LL))(
                         v20,
                         v13,
                         (char *)this + 88);
            if ( Instance >= 0
              || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_53;
            }
            v16 = RdpWppGetCurrentThreadActivityIdPrefix();
            v17 = 40;
            v18 = "Failed to query the connector list";
          }
          else
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_53;
            }
            v16 = RdpWppGetCurrentThreadActivityIdPrefix();
            v17 = 39;
            v18 = "Failed to query the connector list node";
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_53;
          }
          v16 = RdpWppGetCurrentThreadActivityIdPrefix();
          v17 = 37;
          v18 = "Failed to query the auth node";
        }
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v17,
          (unsigned int)WPP_e46c42e76a903292174a4e9de97c4af5_Traceguids,
          v16,
          (__int64)v18,
          Instance);
LABEL_53:
        SysFreeString(v10);
        if ( v12 )
          SysFreeString(v12);
        if ( v13 )
          SysFreeString(v13);
        return (unsigned int)Instance;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_24:
        Instance = -2147024882;
        goto LABEL_53;
      }
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 36;
    }
    else
    {
      v13 = 0;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_24;
      }
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 35;
    }
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      WPP_e46c42e76a903292174a4e9de97c4af5_Traceguids,
      v14,
      -2147024882);
    goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 33;
    v8 = "Failed to deserialize the root element";
    goto LABEL_6;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800f6440  push    rbx
0x1800f6442  push    rbp
0x1800f6443  push    rsi
0x1800f6444  push    rdi
0x1800f6445  push    r12
0x1800f6447  push    r14
0x1800f6449  push    r15
0x1800f644b  sub     rsp, 30h
0x1800f644f  lea     rdi, [rcx+38h]
0x1800f6453  mov     rbp, rdx
0x1800f6456  xor     edx, edx; pUnkOuter
0x1800f6458  mov     [rsp+68h+ppv], rdi; ppv
0x1800f645d  mov     rsi, rcx
0x1800f6460  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x1800f6467  lea     rcx, CLSID_DOMDocument60; rclsid
0x1800f646e  lea     r8d, [rdx+1]; dwClsContext
0x1800f6472  call    cs:__imp_CoCreateInstance
0x1800f6478  mov     ebx, eax
0x1800f647a  test    eax, eax
0x1800f647c  jns     short loc_1800F64E2
0x1800f647e  mov     rax, cs:WPP_GLOBAL_Control
0x1800f6485  lea     rcx, WPP_GLOBAL_Control
0x1800f648c  cmp     rax, rcx
0x1800f648f  jz      loc_1800F6800
0x1800f6495  test    byte ptr [rax+1Ch], 8
0x1800f6499  jz      loc_1800F6800
0x1800f649f  cmp     byte ptr [rax+19h], 2
0x1800f64a3  jb      loc_1800F6800
0x1800f64a9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f64ae  mov     edx, 20h ; ' '
0x1800f64b3  lea     rcx, aFailedToCreate_88; "Failed to create the XML document"
0x1800f64ba  mov     [rsp+68h+var_40], ebx
0x1800f64be  lea     r8, WPP_e46c42e76a903292174a4e9de97c4af5_Traceguids
0x1800f64c5  mov     [rsp+68h+ppv], rcx
0x1800f64ca  mov     r9d, eax
0x1800f64cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f64d4  mov     rcx, [rcx+10h]
0x1800f64d8  call    WPP_SF_DsD
0x1800f64dd  jmp     loc_1800F6800
0x1800f64e2  mov     rcx, [rdi]; struct IXMLDOMNode *
0x1800f64e5  lea     r14, [rsi+40h]
0x1800f64e9  mov     r8, r14; struct IXMLDOMNode **
0x1800f64ec  mov     rdx, rbp; unsigned __int16 *
0x1800f64ef  call    ?RDPENCHLPXML_AddElementFromXMLString@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAU1@@Z; RDPENCHLPXML_AddElementFromXMLString(IXMLDOMNode *,ushort *,IXMLDOMNode * *)
0x1800f64f4  mov     ebx, eax
0x1800f64f6  test    eax, eax
0x1800f64f8  jns     short loc_1800F6538
0x1800f64fa  mov     rax, cs:WPP_GLOBAL_Control
0x1800f6501  lea     rcx, WPP_GLOBAL_Control
0x1800f6508  cmp     rax, rcx
0x1800f650b  jz      loc_1800F6800
0x1800f6511  test    byte ptr [rax+1Ch], 8
0x1800f6515  jz      loc_1800F6800
0x1800f651b  cmp     byte ptr [rax+19h], 2
0x1800f651f  jb      loc_1800F6800
0x1800f6525  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f652a  mov     edx, 21h ; '!'
0x1800f652f  lea     rcx, aFailedToDeseri_0; "Failed to deserialize the root element"
0x1800f6536  jmp     short loc_1800F64BA
0x1800f6538  lea     rcx, aA; "A"
0x1800f653f  call    cs:__imp_SysAllocString
0x1800f6545  mov     r12, rax
0x1800f6548  test    rax, rax
0x1800f654b  jnz     short loc_1800F65A2
0x1800f654d  mov     rax, cs:WPP_GLOBAL_Control
0x1800f6554  lea     rcx, WPP_GLOBAL_Control
0x1800f655b  cmp     rax, rcx
0x1800f655e  jz      short loc_1800F6598
0x1800f6560  test    byte ptr [rax+1Ch], 8
0x1800f6564  jz      short loc_1800F6598
0x1800f6566  cmp     byte ptr [rax+19h], 2
0x1800f656a  jb      short loc_1800F6598
0x1800f656c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f6571  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f6578  lea     edx, [r12+22h]
0x1800f657d  mov     r9d, eax
0x1800f6580  mov     dword ptr [rsp+68h+ppv], 8007000Eh
0x1800f6588  lea     r8, WPP_e46c42e76a903292174a4e9de97c4af5_Traceguids
0x1800f658f  mov     rcx, [rcx+10h]
0x1800f6593  call    WPP_SF_Dd
0x1800f6598  mov     ebx, 8007000Eh
0x1800f659d  jmp     loc_1800F6800
0x1800f65a2  lea     rcx, aC; "C"
0x1800f65a9  call    cs:__imp_SysAllocString
0x1800f65af  mov     rbp, rax
0x1800f65b2  test    rax, rax
0x1800f65b5  jnz     short loc_1800F660C
0x1800f65b7  xor     edi, edi
0x1800f65b9  mov     rdx, cs:WPP_GLOBAL_Control
0x1800f65c0  lea     rcx, WPP_GLOBAL_Control
0x1800f65c7  cmp     rdx, rcx
0x1800f65ca  jz      short loc_1800F6602
0x1800f65cc  test    byte ptr [rdx+1Ch], 8
0x1800f65d0  jz      short loc_1800F6602
0x1800f65d2  cmp     byte ptr [rdx+19h], 2
0x1800f65d6  jb      short loc_1800F6602
0x1800f65d8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f65dd  lea     edx, [rbp+23h]
0x1800f65e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f65e7  lea     r8, WPP_e46c42e76a903292174a4e9de97c4af5_Traceguids
0x1800f65ee  mov     r9d, eax
0x1800f65f1  mov     dword ptr [rsp+68h+ppv], 8007000Eh
0x1800f65f9  mov     rcx, [rcx+10h]
0x1800f65fd  call    WPP_SF_Dd
0x1800f6602  mov     ebx, 8007000Eh
0x1800f6607  jmp     loc_1800F67DB
0x1800f660c  lea     rcx, aTIdAndSid; "T[@ID!='' and @SID!='']"
0x1800f6613  call    cs:__imp_SysAllocString
0x1800f6619  mov     rdi, rax
0x1800f661c  test    rax, rax
0x1800f661f  jnz     short loc_1800F664A
0x1800f6621  mov     rdx, cs:WPP_GLOBAL_Control
0x1800f6628  lea     rcx, WPP_GLOBAL_Control
0x1800f662f  cmp     rdx, rcx
0x1800f6632  jz      short loc_1800F6602
0x1800f6634  test    byte ptr [rdx+1Ch], 8
0x1800f6638  jz      short loc_1800F6602
0x1800f663a  cmp     byte ptr [rdx+19h], 2
0x1800f663e  jb      short loc_1800F6602
0x1800f6640  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f6645  lea     edx, [rdi+24h]
0x1800f6648  jmp     short loc_1800F65E0
0x1800f664a  mov     rcx, [r14]
0x1800f664d  lea     r8, [rsi+48h]
0x1800f6651  mov     rdx, r12
0x1800f6654  mov     rax, [rcx]
0x1800f6657  mov     rax, [rax+128h]
0x1800f665e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6663  mov     ebx, eax
0x1800f6665  test    eax, eax
0x1800f6667  jns     short loc_1800F66AA
0x1800f6669  mov     rax, cs:WPP_GLOBAL_Control
0x1800f6670  lea     rcx, WPP_GLOBAL_Control
0x1800f6677  cmp     rax, rcx
0x1800f667a  jz      loc_1800F67DB
0x1800f6680  test    byte ptr [rax+1Ch], 8
0x1800f6684  jz      loc_1800F67DB
0x1800f668a  cmp     byte ptr [rax+19h], 2
0x1800f668e  jb      loc_1800F67DB
0x1800f6694  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f6699  mov     edx, 25h ; '%'
0x1800f669e  lea     rcx, aFailedToQueryT; "Failed to query the auth node"
0x1800f66a5  jmp     loc_1800F67B8
0x1800f66aa  cmp     qword ptr [rsi+48h], 0
0x1800f66af  jnz     short loc_1800F6706
0x1800f66b1  mov     rax, cs:WPP_GLOBAL_Control
0x1800f66b8  lea     rcx, WPP_GLOBAL_Control
0x1800f66bf  cmp     rax, rcx
0x1800f66c2  jz      short loc_1800F66FC
0x1800f66c4  test    byte ptr [rax+1Ch], 8
0x1800f66c8  jz      short loc_1800F66FC
0x1800f66ca  cmp     byte ptr [rax+19h], 2
0x1800f66ce  jb      short loc_1800F66FC
0x1800f66d0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f66d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f66dc  lea     r8, WPP_e46c42e76a903292174a4e9de97c4af5_Traceguids
0x1800f66e3  mov     edx, 26h ; '&'
0x1800f66e8  mov     dword ptr [rsp+68h+ppv], 8000FFFFh
0x1800f66f0  mov     r9d, eax
0x1800f66f3  mov     rcx, [rcx+10h]
0x1800f66f7  call    WPP_SF_Dd
0x1800f66fc  mov     ebx, 8000FFFFh
0x1800f6701  jmp     loc_1800F67DB
0x1800f6706  mov     rcx, [r14]
0x1800f6709  lea     r8, [rsi+50h]
0x1800f670d  mov     rdx, rbp
0x1800f6710  mov     rax, [rcx]
0x1800f6713  mov     rax, [rax+128h]
0x1800f671a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f671f  mov     ebx, eax
0x1800f6721  test    eax, eax
0x1800f6723  jns     short loc_1800F6763
0x1800f6725  mov     rax, cs:WPP_GLOBAL_Control
0x1800f672c  lea     rcx, WPP_GLOBAL_Control
0x1800f6733  cmp     rax, rcx
0x1800f6736  jz      loc_1800F67DB
0x1800f673c  test    byte ptr [rax+1Ch], 8
0x1800f6740  jz      loc_1800F67DB
0x1800f6746  cmp     byte ptr [rax+19h], 2
0x1800f674a  jb      loc_1800F67DB
0x1800f6750  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f6755  mov     edx, 27h ; '''
0x1800f675a  lea     rcx, aFailedToQueryT_1; "Failed to query the connector list node"
0x1800f6761  jmp     short loc_1800F67B8
0x1800f6763  mov     rcx, [rsi+50h]
0x1800f6767  test    rcx, rcx
0x1800f676a  jz      short loc_1800F67DB
0x1800f676c  mov     rax, [rcx]
0x1800f676f  lea     r8, [rsi+58h]
0x1800f6773  mov     rdx, rdi
0x1800f6776  mov     rax, [rax+120h]
0x1800f677d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6782  mov     ebx, eax
0x1800f6784  test    eax, eax
0x1800f6786  jns     short loc_1800F67DB
0x1800f6788  mov     rax, cs:WPP_GLOBAL_Control
0x1800f678f  lea     rcx, WPP_GLOBAL_Control
0x1800f6796  cmp     rax, rcx
0x1800f6799  jz      short loc_1800F67DB
0x1800f679b  test    byte ptr [rax+1Ch], 8
0x1800f679f  jz      short loc_1800F67DB
0x1800f67a1  cmp     byte ptr [rax+19h], 2
0x1800f67a5  jb      short loc_1800F67DB
0x1800f67a7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f67ac  mov     edx, 28h ; '('
0x1800f67b1  lea     rcx, aFailedToQueryT_6; "Failed to query the connector list"
0x1800f67b8  mov     [rsp+68h+var_40], ebx
0x1800f67bc  lea     r8, WPP_e46c42e76a903292174a4e9de97c4af5_Traceguids
0x1800f67c3  mov     [rsp+68h+ppv], rcx
0x1800f67c8  mov     r9d, eax
0x1800f67cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f67d2  mov     rcx, [rcx+10h]
0x1800f67d6  call    WPP_SF_DsD
0x1800f67db  mov     rcx, r12; bstrString
0x1800f67de  call    cs:__imp_SysFreeString
0x1800f67e4  test    rbp, rbp
0x1800f67e7  jz      short loc_1800F67F2
0x1800f67e9  mov     rcx, rbp; bstrString
0x1800f67ec  call    cs:__imp_SysFreeString
0x1800f67f2  test    rdi, rdi
0x1800f67f5  jz      short loc_1800F6800
0x1800f67f7  mov     rcx, rdi; bstrString
0x1800f67fa  call    cs:__imp_SysFreeString
0x1800f6800  mov     eax, ebx
0x1800f6802  add     rsp, 30h
0x1800f6806  pop     r15
0x1800f6808  pop     r14
0x1800f680a  pop     r12
0x1800f680c  pop     rdi
0x1800f680d  pop     rsi
0x1800f680e  pop     rbp
0x1800f680f  pop     rbx
0x1800f6810  retn
```
