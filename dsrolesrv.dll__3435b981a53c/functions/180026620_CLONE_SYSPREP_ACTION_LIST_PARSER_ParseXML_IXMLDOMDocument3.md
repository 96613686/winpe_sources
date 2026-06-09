# CLONE_SYSPREP_ACTION_LIST_PARSER::ParseXML(IXMLDOMDocument3 *)

- ea: `0x180026620`
- end: `0x180026901`
- name: `?ParseXML@CLONE_SYSPREP_ACTION_LIST_PARSER@@UEAAJPEAUIXMLDOMDocument3@@@Z`
- size: `737`
- prototype: `__int64 __fastcall(CLONE_SYSPREP_ACTION_LIST **this, struct IXMLDOMDocument3 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callees

- `0x1800254ec`
- `0x180025890`
- `0x180026620`
- `0x1800273e4`
- `0x18002c050`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267fb`
- `WDSCORE!WdsSetupLogMessageW` at `0x180026862`
- `WDSCORE!WdsSetupLogMessageW` at `0x180026862`
- `WDSCORE!CurrentIP` at `0x180026803`
- `WDSCORE!CurrentIP` at `0x180026803`
- `OLEAUT32!__imp_SysAllocString` at `0x1800266bb`
- `OLEAUT32!__imp_SysAllocString` at `0x1800266bb`
- `OLEAUT32!__imp_SysFreeString` at `0x18002676f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800267a0`
- `OLEAUT32!__imp_SysFreeString` at `0x180026883`
- `OLEAUT32!__imp_SysFreeString` at `0x1800268c1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800268cc`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c77b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c7bc`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c7c6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002676f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800267a0`
- `OLEAUT32!__imp_SysFreeString` at `0x180026883`
- `OLEAUT32!__imp_SysFreeString` at `0x1800268c1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800268cc`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c77b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c7bc`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c7c6`

## string_xrefs

- `0x180026830`: `CLONE_SYSPREP_ACTION_LIST_PARSER::ParseXML`

## pseudocode

```c
__int64 __fastcall CLONE_SYSPREP_ACTION_LIST_PARSER::ParseXML(
        CLONE_SYSPREP_ACTION_LIST **this,
        struct IXMLDOMDocument3 *a2)
{
  BSTR v4; // rdx
  unsigned __int16 *v5; // rsi
  unsigned __int16 *v6; // r14
  int v7; // ebx
  OLECHAR *v8; // rax
  int NodeText; // ebx
  int v10; // eax
  struct IXMLDOMNode *v11; // rcx
  DWORD LastError; // edi
  __int64 v13; // rbx
  struct tagLOG_PARTIAL_MSG *v14; // rax
  unsigned int i; // edi
  struct IXMLDOMNode *v17; // [rsp+60h] [rbp-88h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-80h] BYREF
  BSTR v19; // [rsp+70h] [rbp-78h] BYREF
  __int64 v20; // [rsp+78h] [rbp-70h] BYREF
  int v21; // [rsp+80h] [rbp-68h]
  OLECHAR *psz; // [rsp+88h] [rbp-60h]
  BSTR v23[2]; // [rsp+90h] [rbp-58h]
  unsigned __int16 *v24; // [rsp+A0h] [rbp-48h]
  const wchar_t *v25; // [rsp+A8h] [rbp-40h]
  unsigned __int16 *v26; // [rsp+B0h] [rbp-38h]

  v20 = 0;
  v17 = 0;
  bstrString = 0;
  v19 = 0;
  psz = L"//sysprepInformation/imaging/sysprepModule";
  v4 = 0;
  v23[0] = 0;
  v23[1] = L"@methodName";
  v5 = 0;
  v24 = 0;
  v25 = L"@moduleName";
  v6 = 0;
  v26 = 0;
  v7 = 0;
  while ( 1 )
  {
    v21 = v7;
    if ( (unsigned __int64)v7 >= 3 )
      break;
    v8 = SysAllocString(v23[2 * v7 - 1]);
    v23[2 * v7] = v8;
    if ( !v8 )
    {
      NodeText = 14;
      goto LABEL_28;
    }
    ++v7;
    v6 = v26;
    v5 = v24;
    v4 = v23[0];
  }
  v10 = ((__int64 (__fastcall *)(struct IXMLDOMDocument3 *, BSTR, __int64 *))a2->lpVtbl->selectNodes)(a2, v4, &v20);
  if ( v10 )
  {
    NodeText = 0;
    if ( v10 != 1 )
      NodeText = v10;
  }
  else
  {
    while ( 1 )
    {
      if ( v17 )
      {
        ((void (__fastcall *)(struct IXMLDOMNode *))v17->lpVtbl->Release)(v17);
        v17 = 0;
      }
      if ( (*(unsigned int (__fastcall **)(__int64, struct IXMLDOMNode **))(*(_QWORD *)v20 + 72LL))(v20, &v17) )
        break;
      v11 = v17;
      if ( !v17 )
        break;
      if ( bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
        v11 = v17;
      }
      NodeText = getNodeText(v11, v6, &bstrString);
      if ( NodeText < 0 )
        goto LABEL_28;
      if ( v19 )
      {
        SysFreeString(v19);
        v19 = 0;
      }
      NodeText = getNodeText(v17, v5, &v19);
      if ( NodeText < 0 )
        goto LABEL_28;
      if ( !bstrString || !*bstrString || !v19 || !*v19 )
      {
        LastError = GetLastError();
        v13 = CurrentIP();
        v14 = ConstructPartialMsgW(0x2000000, "Module node has empty methodName or moduleName");
        WdsSetupLogMessageW(
          v14,
          983040,
          L"D",
          0,
          722,
          L"ds\\ds\\src\\util\\clonelib\\clsysprep.cxx",
          L"CLONE_SYSPREP_ACTION_LIST_PARSER::ParseXML",
          v13,
          LastError,
          0,
          0);
        NodeText = -2147467259;
        goto LABEL_28;
      }
      NodeText = CLONE_SYSPREP_ACTION_LIST::AddActionEntry(this[1], v19, bstrString);
      if ( NodeText )
        goto LABEL_28;
    }
    NodeText = 0;
  }
LABEL_28:
  for ( i = 0; i < 3; ++i )
    SysFreeString(v23[2 * (int)i]);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v17 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v17->lpVtbl->Release)(v17);
  SysFreeString(bstrString);
  SysFreeString(v19);
  return (unsigned int)NodeText;
}

```

## disassembly

```asm
0x180026620  mov     r11, rsp
0x180026623  mov     [r11+18h], rbx
0x180026627  mov     [r11+20h], rsi
0x18002662b  push    rdi
0x18002662c  push    r12
0x18002662e  push    r13
0x180026630  push    r14
0x180026632  push    r15
0x180026634  sub     rsp, 0C0h
0x18002663b  mov     rax, cs:__security_cookie
0x180026642  xor     rax, rsp
0x180026645  mov     [rsp+0E8h+var_30], rax
0x18002664d  mov     r15, rdx
0x180026650  mov     r13, rcx
0x180026653  xor     r12d, r12d
0x180026656  mov     [r11-70h], r12
0x18002665a  mov     [rsp+0E8h+var_88], r12
0x18002665f  mov     [r11-80h], r12
0x180026663  mov     [r11-78h], r12
0x180026667  lea     rax, aSysprepinforma; "//sysprepInformation/imaging/sysprepMod"...
0x18002666e  mov     [r11-60h], rax
0x180026672  mov     edx, r12d
0x180026675  mov     [r11-58h], rdx
0x180026679  lea     rax, aMethodname; "@methodName"
0x180026680  mov     [r11-50h], rax
0x180026684  mov     esi, r12d
0x180026687  mov     [r11-48h], r12
0x18002668b  lea     rax, aModulename; "@moduleName"
0x180026692  mov     [r11-40h], rax
0x180026696  mov     r14d, r12d
0x180026699  mov     [r11-38h], r12
0x18002669d  mov     ebx, r12d
0x1800266a0  mov     [rsp+0E8h+var_68], ebx
0x1800266a7  movsxd  rdi, ebx
0x1800266aa  cmp     rdi, 3
0x1800266ae  jnb     short loc_1800266F2
0x1800266b0  add     rdi, rdi
0x1800266b3  mov     rcx, [rsp+rdi*8+0E8h+psz]; psz
0x1800266bb  call    cs:__imp_SysAllocString
0x1800266c1  mov     [rsp+rdi*8+0E8h+var_58], rax
0x1800266c9  test    rax, rax
0x1800266cc  jnz     short loc_1800266D6
0x1800266ce  lea     ebx, [rax+0Eh]
0x1800266d1  jmp     loc_180026872
0x1800266d6  inc     ebx
0x1800266d8  mov     r14, [rsp+0E8h+var_38]
0x1800266e0  mov     rsi, [rsp+0E8h+var_48]
0x1800266e8  mov     rdx, [rsp+0E8h+var_58]
0x1800266f0  jmp     short loc_1800266A0
0x1800266f2  mov     rax, [r15]
0x1800266f5  lea     r8, [rsp+0E8h+var_70]
0x1800266fa  mov     rcx, r15
0x1800266fd  mov     rax, [rax+120h]
0x180026704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026709  test    eax, eax
0x18002670b  jz      short loc_18002671B
0x18002670d  mov     ebx, r12d
0x180026710  cmp     eax, 1
0x180026713  cmovnz  ebx, eax
0x180026716  jmp     loc_180026872
0x18002671b  mov     rcx, [rsp+0E8h+var_88]
0x180026720  test    rcx, rcx
0x180026723  jz      short loc_180026736
0x180026725  mov     rax, [rcx]
0x180026728  mov     rax, [rax+10h]
0x18002672c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026731  mov     [rsp+0E8h+var_88], r12
0x180026736  mov     rcx, [rsp+0E8h+var_70]
0x18002673b  mov     rax, [rcx]
0x18002673e  lea     rdx, [rsp+0E8h+var_88]
0x180026743  mov     rax, [rax+48h]
0x180026747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002674c  test    eax, eax
0x18002674e  jnz     loc_18002686F
0x180026754  mov     rcx, [rsp+0E8h+var_88]
0x180026759  test    rcx, rcx
0x18002675c  jz      loc_18002686F
0x180026762  mov     rax, [rsp+0E8h+bstrString]
0x180026767  test    rax, rax
0x18002676a  jz      short loc_18002677F
0x18002676c  mov     rcx, rax; bstrString
0x18002676f  call    cs:__imp_SysFreeString
0x180026775  mov     [rsp+0E8h+bstrString], r12
0x18002677a  mov     rcx, [rsp+0E8h+var_88]; struct IXMLDOMNode *
0x18002677f  lea     r8, [rsp+0E8h+bstrString]; unsigned __int16 **
0x180026784  mov     rdx, r14; unsigned __int16 *
0x180026787  call    ?getNodeText@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; getNodeText(IXMLDOMNode *,ushort *,ushort * *)
0x18002678c  mov     ebx, eax
0x18002678e  test    eax, eax
0x180026790  js      loc_180026872
0x180026796  mov     rcx, [rsp+0E8h+var_78]; bstrString
0x18002679b  test    rcx, rcx
0x18002679e  jz      short loc_1800267AB
0x1800267a0  call    cs:__imp_SysFreeString
0x1800267a6  mov     [rsp+0E8h+var_78], r12
0x1800267ab  lea     r8, [rsp+0E8h+var_78]; unsigned __int16 **
0x1800267b0  mov     rdx, rsi; unsigned __int16 *
0x1800267b3  mov     rcx, [rsp+0E8h+var_88]; struct IXMLDOMNode *
0x1800267b8  call    ?getNodeText@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; getNodeText(IXMLDOMNode *,ushort *,ushort * *)
0x1800267bd  mov     ebx, eax
0x1800267bf  test    eax, eax
0x1800267c1  js      loc_180026872
0x1800267c7  mov     r8, [rsp+0E8h+bstrString]; unsigned __int16 *
0x1800267cc  test    r8, r8
0x1800267cf  jz      short loc_1800267FB
0x1800267d1  cmp     [r8], r12w
0x1800267d5  jz      short loc_1800267FB
0x1800267d7  mov     rdx, [rsp+0E8h+var_78]; unsigned __int16 *
0x1800267dc  test    rdx, rdx
0x1800267df  jz      short loc_1800267FB
0x1800267e1  cmp     [rdx], r12w
0x1800267e5  jz      short loc_1800267FB
0x1800267e7  mov     rcx, [r13+8]; this
0x1800267eb  call    ?AddActionEntry@CLONE_SYSPREP_ACTION_LIST@@QEAAKPEAG0@Z; CLONE_SYSPREP_ACTION_LIST::AddActionEntry(ushort *,ushort *)
0x1800267f0  mov     ebx, eax
0x1800267f2  test    eax, eax
0x1800267f4  jnz     short loc_180026872
0x1800267f6  jmp     loc_18002671B
0x1800267fb  call    cs:__imp_GetLastError
0x180026801  mov     edi, eax
0x180026803  call    cs:__imp_CurrentIP
0x180026809  mov     rbx, rax
0x18002680c  lea     rdx, aModuleNodeHasE; "Module node has empty methodName or mod"...
0x180026813  mov     ecx, 2000000h; unsigned int
0x180026818  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18002681d  mov     [rsp+0E8h+var_98], r12d
0x180026822  mov     [rsp+0E8h+var_A0], r12
0x180026827  mov     [rsp+0E8h+var_A8], edi
0x18002682b  mov     [rsp+0E8h+var_B0], rbx
0x180026830  lea     rcx, aCloneSysprepAc_0; "CLONE_SYSPREP_ACTION_LIST_PARSER::Parse"...
0x180026837  mov     [rsp+0E8h+var_B8], rcx
0x18002683c  lea     rcx, aDsDsSrcUtilClo; "ds\\ds\\src\\util\\clonelib\\clsysprep."...
0x180026843  mov     [rsp+0E8h+var_C0], rcx
0x180026848  mov     [rsp+0E8h+var_C8], 2D2h
0x180026850  xor     r9d, r9d
0x180026853  lea     r8, aD_0; "D"
0x18002685a  mov     edx, 0F0000h
0x18002685f  mov     rcx, rax
0x180026862  call    cs:__imp_WdsSetupLogMessageW
0x180026868  mov     ebx, 80004005h
0x18002686d  jmp     short loc_180026872
0x18002686f  mov     ebx, r12d
0x180026872  mov     edi, r12d
0x180026875  movsxd  rcx, edi
0x180026878  add     rcx, rcx
0x18002687b  mov     rcx, [rsp+rcx*8+0E8h+var_58]; bstrString
0x180026883  call    cs:__imp_SysFreeString
0x180026889  inc     edi
0x18002688b  cmp     edi, 3
0x18002688e  jb      short loc_180026875
0x180026890  mov     rcx, [rsp+0E8h+var_70]
0x180026895  test    rcx, rcx
0x180026898  jz      short loc_1800268A6
0x18002689a  mov     rax, [rcx]
0x18002689d  mov     rax, [rax+10h]
0x1800268a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268a6  mov     rcx, [rsp+0E8h+var_88]
0x1800268ab  test    rcx, rcx
0x1800268ae  jz      short loc_1800268BC
0x1800268b0  mov     rax, [rcx]
0x1800268b3  mov     rax, [rax+10h]
0x1800268b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268bc  mov     rcx, [rsp+0E8h+bstrString]; bstrString
0x1800268c1  call    cs:__imp_SysFreeString
0x1800268c7  mov     rcx, [rsp+0E8h+var_78]; bstrString
0x1800268cc  call    cs:__imp_SysFreeString
0x1800268d2  mov     eax, ebx
0x1800268d4  mov     rcx, [rsp+0E8h+var_30]
0x1800268dc  xor     rcx, rsp; StackCookie
0x1800268df  call    __security_check_cookie
0x1800268e4  lea     r11, [rsp+0E8h+var_28]
0x1800268ec  mov     rbx, [r11+40h]
0x1800268f0  mov     rsi, [r11+48h]
0x1800268f4  mov     rsp, r11
0x1800268f7  pop     r15
0x1800268f9  pop     r14
0x1800268fb  pop     r13
0x1800268fd  pop     r12
0x1800268ff  pop     rdi
0x180026900  retn
0x18002c761  push    rbx
0x18002c763  push    rbp
0x18002c764  sub     rsp, 68h
0x18002c768  mov     rbp, rdx
0x18002c76b  xor     ebx, ebx
0x18002c76d  movsxd  rcx, ebx
0x18002c770  add     rcx, rcx
0x18002c773  mov     rcx, [rbp+rcx*8+90h]; bstrString
0x18002c77b  call    cs:__imp_SysFreeString
0x18002c781  inc     ebx
0x18002c783  movsxd  rax, ebx
0x18002c786  cmp     rax, 3
0x18002c78a  jb      short loc_18002C76D
0x18002c78c  mov     rcx, [rbp+78h]
0x18002c790  test    rcx, rcx
0x18002c793  jz      short loc_18002C7A2
0x18002c795  mov     rax, [rcx]
0x18002c798  mov     rax, [rax+10h]
0x18002c79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7a1  nop
0x18002c7a2  mov     rcx, [rbp+60h]
0x18002c7a6  test    rcx, rcx
0x18002c7a9  jz      short loc_18002C7B8
0x18002c7ab  mov     rax, [rcx]
0x18002c7ae  mov     rax, [rax+10h]
0x18002c7b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7b7  nop
0x18002c7b8  mov     rcx, [rbp+68h]; bstrString
0x18002c7bc  call    cs:__imp_SysFreeString
0x18002c7c2  mov     rcx, [rbp+70h]; bstrString
0x18002c7c6  call    cs:__imp_SysFreeString
0x18002c7cc  nop
0x18002c7cd  add     rsp, 68h
0x18002c7d1  pop     rbp
0x18002c7d2  pop     rbx
0x18002c7d3  retn
```
