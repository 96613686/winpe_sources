# CResultViewType::ScInitialize(_RESULT_VIEW_TYPE_INFO &,bool)

- ea: `0x1800c4d08`
- end: `0x1800c4f27`
- name: `?ScInitialize@CResultViewType@@QEAA?AVSC@mmcerror@@AEAU_RESULT_VIEW_TYPE_INFO@@_N@Z`
- size: `543`
- prototype: `mmcerror::SC *__fastcall(__int64, mmcerror::SC *, _QWORD *, unsigned __int8)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800505bc`
- `0x1800c3cac`

## callees

- `0x1800139a4`
- `0x180015830`
- `0x1800c4d08`
- `0x18013f010`

## import_xrefs

- `mmcbase!?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z` at `0x1800c4d84`
- `mmcbase!?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z` at `0x1800c4d84`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1800c4d29`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1800c4d29`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800c4d50`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800c4d73`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800c4dc0`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800c4e0c`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800c4e2e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800c4e7d`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800c4e9f`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800c4eec`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800c4d50`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800c4d73`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800c4dc0`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800c4e0c`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800c4e2e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800c4e7d`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800c4e9f`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800c4eec`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1800c4f08`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1800c4f08`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1800c4d3b`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1800c4d3b`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800c4f13`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800c4f13`
- `ole32!CoTaskMemFree` at `0x1800c4d9b`
- `ole32!CoTaskMemFree` at `0x1800c4ec9`
- `ole32!CoTaskMemFree` at `0x1800c4d9b`
- `ole32!CoTaskMemFree` at `0x1800c4ec9`

## pseudocode

```c
mmcerror::SC *__fastcall CResultViewType::ScInitialize(__int64 a1, mmcerror::SC *a2, _QWORD *a3, unsigned __int8 a4)
{
  int v4; // r14d
  __int64 v8; // rdx
  const struct mmcerror::SC *v9; // rdx
  const unsigned __int16 *v10; // rcx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  int v13; // eax
  int v14; // eax
  _BYTE v16[24]; // [rsp+28h] [rbp-18h] BYREF

  v4 = a4;
  mmcerror::SC::SC((mmcerror::SC *)v16, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v16, L"CResultViewType::ScInitialize");
  if ( !*(_BYTE *)(a1 + 9) )
  {
    *(_BYTE *)(a1 + 9) = 1;
    if ( *a3 )
    {
      std::wstring::assign(a1 + 80, *a3);
      CoTaskMemFree((LPVOID)*a3);
      *a3 = 0;
      *(_BYTE *)(a1 + 8) = 1;
      v11 = *((_DWORD *)a3 + 2);
      *(_DWORD *)(a1 + 12) = v11;
      if ( v11 <= 2 )
      {
        *(_DWORD *)(a1 + 116) = *((_DWORD *)a3 + 3);
        *(_DWORD *)(a1 + 112) = v4;
        if ( v11 )
        {
          v12 = v11 - 1;
          if ( v12 )
          {
            if ( v12 != 1 )
            {
              v8 = 2147942487LL;
              goto LABEL_3;
            }
            v13 = *((_DWORD *)a3 + 4);
            if ( (v13 & 0xFFFFFFFC) != 0 )
            {
              mmcerror::SC::operator=(v16, 2147942487LL);
              v10 = L"Parameter 'dwOCXOptions' in structure 'RESULT_VIEW_TYPE_INFO' is invalid";
            }
            else
            {
              if ( a3[3] )
              {
                *(_DWORD *)(a1 + 128) = v13;
                ATL::AtlComPtrAssign((struct IUnknown **)(a1 + 136), (struct IUnknown *)a3[3]);
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)a3[3] + 16LL))(a3[3]);
                goto LABEL_26;
              }
              mmcerror::SC::operator=(v16, 2147942487LL);
              v10 = L"No OCX specified in parameter 'pUnkControl' of structure 'RESULT_VIEW_TYPE_INFO'";
            }
          }
          else if ( (a3[2] & 0xFFFFFFFE) != 0 )
          {
            mmcerror::SC::operator=(v16, 2147942487LL);
            v10 = L"Parameter 'dwHTMLOptions' in structure 'RESULT_VIEW_TYPE_INFO' must be zero";
          }
          else
          {
            if ( a3[3] )
            {
              *(_DWORD *)(a1 + 124) = 0;
              std::wstring::assign(a1 + 16, a3[3]);
              CoTaskMemFree((LPVOID)a3[3]);
              a3[3] = 0;
              goto LABEL_26;
            }
            mmcerror::SC::operator=(v16, 2147942487LL);
            v10 = L"Parameter 'pstrURL' in structure 'RESULT_VIEW_TYPE_INFO' cannot be NULL";
          }
        }
        else
        {
          v14 = *((_DWORD *)a3 + 4);
          if ( (v14 & 0xFFFFFE11) == 0 )
          {
            *(_DWORD *)(a1 + 120) = v14;
            goto LABEL_26;
          }
          mmcerror::SC::operator=(v16, 2147942487LL);
          v10 = L"Parameter 'dwListOptions' in structure 'RESULT_VIEW_TYPE_INFO' is invalid";
        }
      }
      else
      {
        mmcerror::SC::operator=(v16, 2147942487LL);
        v10 = L"Parameter 'eViewType' in structure 'RESULT_VIEW_TYPE_INFO' is invalid";
      }
    }
    else
    {
      mmcerror::SC::operator=(v16, 2147942487LL);
      v10 = L"Parameter 'pstrPersistableViewDescription' in structure 'RESULT_VIEW_TYPE_INFO' is NULL";
    }
    TraceSnapinError(v10, (const struct mmcerror::SC *)v16);
LABEL_26:
    v9 = (const struct mmcerror::SC *)v16;
    goto LABEL_27;
  }
  v8 = 2147549183LL;
LABEL_3:
  v9 = (const struct mmcerror::SC *)mmcerror::SC::operator=(v16, v8);
LABEL_27:
  mmcerror::SC::SC(a2, v9);
  mmcerror::SC::~SC((mmcerror::SC *)v16);
  return a2;
}

```

## disassembly

```asm
0x1800c4d08  push    rbp
0x1800c4d0a  push    rbx
0x1800c4d0b  push    rsi
0x1800c4d0c  push    rdi
0x1800c4d0d  push    r14
0x1800c4d0f  mov     rbp, rsp
0x1800c4d12  sub     rsp, 40h
0x1800c4d16  movzx   r14d, r9b
0x1800c4d1a  mov     rdi, r8
0x1800c4d1d  mov     rbx, rdx
0x1800c4d20  mov     rsi, rcx
0x1800c4d23  xor     edx, edx
0x1800c4d25  lea     rcx, [rbp+var_18]
0x1800c4d29  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x1800c4d2f  nop
0x1800c4d30  lea     rdx, aCresultviewtyp_0; "CResultViewType::ScInitialize"
0x1800c4d37  lea     rcx, [rbp+var_18]
0x1800c4d3b  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x1800c4d41  cmp     byte ptr [rsi+9], 0
0x1800c4d45  jz      short loc_1800C4D5E
0x1800c4d47  mov     edx, 8000FFFFh
0x1800c4d4c  lea     rcx, [rbp+var_18]
0x1800c4d50  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1800c4d56  mov     rdx, rax
0x1800c4d59  jmp     loc_1800C4F05
0x1800c4d5e  mov     byte ptr [rsi+9], 1
0x1800c4d62  mov     rdx, [rdi]
0x1800c4d65  test    rdx, rdx
0x1800c4d68  jnz     short loc_1800C4D8F
0x1800c4d6a  mov     edx, 80070057h
0x1800c4d6f  lea     rcx, [rbp+var_18]
0x1800c4d73  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1800c4d79  lea     rcx, aParameterPstrp; "Parameter 'pstrPersistableViewDescripti"...
0x1800c4d80  lea     rdx, [rbp+var_18]
0x1800c4d84  call    cs:__imp_?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z; TraceSnapinError(ushort const *,mmcerror::SC const &)
0x1800c4d8a  jmp     loc_1800C4F01
0x1800c4d8f  lea     rcx, [rsi+50h]
0x1800c4d93  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800c4d98  mov     rcx, [rdi]; pv
0x1800c4d9b  call    cs:__imp_CoTaskMemFree
0x1800c4da1  mov     qword ptr [rdi], 0
0x1800c4da8  mov     byte ptr [rsi+8], 1
0x1800c4dac  mov     ecx, [rdi+8]
0x1800c4daf  mov     [rsi+0Ch], ecx
0x1800c4db2  cmp     ecx, 2
0x1800c4db5  jbe     short loc_1800C4DCF
0x1800c4db7  mov     edx, 80070057h
0x1800c4dbc  lea     rcx, [rbp+var_18]
0x1800c4dc0  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1800c4dc6  lea     rcx, aParameterEview; "Parameter 'eViewType' in structure 'RES"...
0x1800c4dcd  jmp     short loc_1800C4D80
0x1800c4dcf  mov     eax, [rdi+0Ch]
0x1800c4dd2  mov     [rsi+74h], eax
0x1800c4dd5  mov     [rsi+70h], r14d
0x1800c4dd9  test    ecx, ecx
0x1800c4ddb  jz      loc_1800C4ED9
0x1800c4de1  sub     ecx, 1
0x1800c4de4  jz      loc_1800C4E6B
0x1800c4dea  cmp     ecx, 1
0x1800c4ded  jz      short loc_1800C4DF9
0x1800c4def  mov     edx, 80070057h
0x1800c4df4  jmp     loc_1800C4D4C
0x1800c4df9  mov     eax, [rdi+10h]
0x1800c4dfc  test    eax, 0FFFFFFFCh
0x1800c4e01  jz      short loc_1800C4E1E
0x1800c4e03  mov     edx, 80070057h
0x1800c4e08  lea     rcx, [rbp+var_18]
0x1800c4e0c  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1800c4e12  lea     rcx, aParameterDwocx; "Parameter 'dwOCXOptions' in structure '"...
0x1800c4e19  jmp     loc_1800C4D80
0x1800c4e1e  cmp     qword ptr [rdi+18h], 0
0x1800c4e23  jnz     short loc_1800C4E40
0x1800c4e25  mov     edx, 80070057h
0x1800c4e2a  lea     rcx, [rbp+var_18]
0x1800c4e2e  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1800c4e34  lea     rcx, aNoOcxSpecified; "No OCX specified in parameter 'pUnkCont"...
0x1800c4e3b  jmp     loc_1800C4D80
0x1800c4e40  mov     [rsi+80h], eax
0x1800c4e46  lea     rcx, [rsi+88h]; struct IUnknown **
0x1800c4e4d  mov     rdx, [rdi+18h]; struct IUnknown *
0x1800c4e51  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800c4e56  mov     rcx, [rdi+18h]
0x1800c4e5a  mov     rax, [rcx]
0x1800c4e5d  mov     rax, [rax+10h]
0x1800c4e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4e66  jmp     loc_1800C4F01
0x1800c4e6b  test    dword ptr [rdi+10h], 0FFFFFFFEh
0x1800c4e72  jz      short loc_1800C4E8F
0x1800c4e74  mov     edx, 80070057h
0x1800c4e79  lea     rcx, [rbp+var_18]
0x1800c4e7d  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1800c4e83  lea     rcx, aParameterDwhtm; "Parameter 'dwHTMLOptions' in structure "...
0x1800c4e8a  jmp     loc_1800C4D80
0x1800c4e8f  cmp     qword ptr [rdi+18h], 0
0x1800c4e94  jnz     short loc_1800C4EB1
0x1800c4e96  mov     edx, 80070057h
0x1800c4e9b  lea     rcx, [rbp+var_18]
0x1800c4e9f  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1800c4ea5  lea     rcx, aParameterPstru; "Parameter 'pstrURL' in structure 'RESUL"...
0x1800c4eac  jmp     loc_1800C4D80
0x1800c4eb1  mov     dword ptr [rsi+7Ch], 0
0x1800c4eb8  lea     rcx, [rsi+10h]
0x1800c4ebc  mov     rdx, [rdi+18h]
0x1800c4ec0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800c4ec5  mov     rcx, [rdi+18h]; pv
0x1800c4ec9  call    cs:__imp_CoTaskMemFree
0x1800c4ecf  mov     qword ptr [rdi+18h], 0
0x1800c4ed7  jmp     short loc_1800C4F01
0x1800c4ed9  mov     eax, [rdi+10h]
0x1800c4edc  test    eax, 0FFFFFE11h
0x1800c4ee1  jz      short loc_1800C4EFE
0x1800c4ee3  mov     edx, 80070057h
0x1800c4ee8  lea     rcx, [rbp+var_18]
0x1800c4eec  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1800c4ef2  lea     rcx, aParameterDwlis; "Parameter 'dwListOptions' in structure "...
0x1800c4ef9  jmp     loc_1800C4D80
0x1800c4efe  mov     [rsi+78h], eax
0x1800c4f01  lea     rdx, [rbp+var_18]
0x1800c4f05  mov     rcx, rbx
0x1800c4f08  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x1800c4f0e  nop
0x1800c4f0f  lea     rcx, [rbp+var_18]
0x1800c4f13  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1800c4f19  mov     rax, rbx
0x1800c4f1c  add     rsp, 40h
0x1800c4f20  pop     r14
0x1800c4f22  pop     rdi
0x1800c4f23  pop     rsi
0x1800c4f24  pop     rbx
0x1800c4f25  pop     rbp
0x1800c4f26  retn
```
