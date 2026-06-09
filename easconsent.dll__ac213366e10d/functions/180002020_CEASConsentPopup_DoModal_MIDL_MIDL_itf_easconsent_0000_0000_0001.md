# CEASConsentPopup::DoModal(__MIDL___MIDL_itf_easconsent_0000_0000_0001 *)

- ea: `0x180002020`
- end: `0x1800021ad`
- name: `?DoModal@CEASConsentPopup@@UEAAJPEAW4__MIDL___MIDL_itf_easconsent_0000_0000_0001@@@Z`
- size: `397`
- prototype: `__int64 __fastcall(CEASConsentPopup *this, enum __MIDL___MIDL_itf_easconsent_0000_0000_0001 *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callees

- `0x180002020`
- `0x1800026f8`
- `0x180004010`

## import_xrefs

- `USER32!GetMessageW` at `0x18000215e`
- `USER32!GetMessageW` at `0x18000215e`
- `USER32!DispatchMessageW` at `0x18000214c`
- `USER32!DispatchMessageW` at `0x18000214c`
- `USER32!TranslateMessage` at `0x180002142`
- `USER32!TranslateMessage` at `0x180002142`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1800020f6`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1800020f6`
- `DUI70!UnInitProcessPriv` at `0x180002195`
- `DUI70!UnInitProcessPriv` at `0x180002195`
- `DUI70!UnInitThread` at `0x180002188`
- `DUI70!UnInitThread` at `0x180002188`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180002182`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180002182`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180002178`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180002178`
- `DUI70!InitProcessPriv` at `0x180002052`
- `DUI70!InitProcessPriv` at `0x180002052`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800020bb`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800020bb`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180002094`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180002094`
- `DUI70!InitThread` at `0x180002067`
- `DUI70!InitThread` at `0x180002067`

## pseudocode

```c
__int64 __fastcall CEASConsentPopup::DoModal(
        CEASConsentPopup *this,
        enum __MIDL___MIDL_itf_easconsent_0000_0000_0001 *a2,
        __int64 a3)
{
  int inited; // ebx
  MSG Msg; // [rsp+30h] [rbp-30h] BYREF
  struct DirectUI::DUIXmlParser *v8; // [rsp+88h] [rbp+28h] BYREF
  struct DirectUI::Element *v9; // [rsp+90h] [rbp+30h] BYREF

  *(_DWORD *)a2 = 0;
  LOBYTE(a3) = 1;
  inited = InitProcessPriv(14, 0x180000000uLL, a3);
  if ( inited >= 0 )
  {
    inited = InitThread(65538);
    if ( inited >= 0 )
    {
      v8 = 0;
      inited = DirectUI::DUIXmlParser::Create(&v8, 0, 0, 0, 0);
      if ( inited >= 0 )
      {
        inited = DirectUI::DUIXmlParser::SetXMLFromResource(
                   v8,
                   0x2711u,
                   (HINSTANCE)0x180000000LL,
                   (HINSTANCE)0x180000000LL);
        if ( inited >= 0 )
        {
          v9 = 0;
          inited = DirectUI::DUIXmlParser::CreateElement(v8, L"ConsentPopup", 0, 0, 0, &v9);
          if ( inited >= 0 )
          {
            inited = CEASConsentPopup::_CreateConsentPopup(this, &v9);
            if ( inited >= 0 )
            {
              inited = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 272LL))(*((_QWORD *)this + 4));
              if ( inited >= 0 )
              {
                memset(&Msg, 0, sizeof(Msg));
                while ( GetMessageW(&Msg, 0, 0, 0) )
                {
                  TranslateMessage(&Msg);
                  DispatchMessageW(&Msg);
                }
                *(_DWORD *)a2 = *((_DWORD *)this + 6);
              }
            }
            if ( v9 )
              DirectUI::Element::Destroy(v9, 1);
          }
        }
        DirectUI::DUIXmlParser::Destroy(v8);
      }
      UnInitThread();
    }
    UnInitProcessPriv(0x180000000uLL);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180002020  mov     [rsp-18h+arg_0], rbx
0x180002025  push    rbp
0x180002026  push    rsi
0x180002027  push    rdi
0x180002028  mov     rbp, rsp
0x18000202b  sub     rsp, 60h
0x18000202f  mov     r9b, 1
0x180002032  mov     dword ptr [rdx], 0
0x180002038  mov     rsi, rdx
0x18000203b  mov     byte ptr [rsp+60h+var_40], 1
0x180002040  mov     rdi, rcx
0x180002043  lea     rdx, cs:180000000h
0x18000204a  mov     r8b, r9b
0x18000204d  mov     ecx, 0Eh
0x180002052  call    cs:__imp_InitProcessPriv
0x180002058  mov     ebx, eax
0x18000205a  test    eax, eax
0x18000205c  js      loc_18000219B
0x180002062  mov     ecx, 10002h
0x180002067  call    cs:__imp_InitThread
0x18000206d  mov     ebx, eax
0x18000206f  test    eax, eax
0x180002071  js      loc_18000218E
0x180002077  xor     r9d, r9d
0x18000207a  mov     [rbp+arg_8], 0
0x180002082  xor     r8d, r8d
0x180002085  mov     [rsp+60h+var_40], 0
0x18000208e  xor     edx, edx
0x180002090  lea     rcx, [rbp+arg_8]
0x180002094  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x18000209a  mov     ebx, eax
0x18000209c  test    eax, eax
0x18000209e  js      loc_180002188
0x1800020a4  mov     rcx, [rbp+arg_8]
0x1800020a8  lea     r9, cs:180000000h
0x1800020af  lea     r8, cs:180000000h
0x1800020b6  mov     edx, 2711h
0x1800020bb  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x1800020c1  mov     ebx, eax
0x1800020c3  test    eax, eax
0x1800020c5  js      loc_18000217E
0x1800020cb  mov     rcx, [rbp+arg_8]
0x1800020cf  lea     rax, [rbp+arg_10]
0x1800020d3  mov     [rsp+60h+var_38], rax
0x1800020d8  lea     rdx, aConsentpopup; "ConsentPopup"
0x1800020df  xor     r9d, r9d
0x1800020e2  mov     [rsp+60h+var_40], 0
0x1800020eb  xor     r8d, r8d
0x1800020ee  mov     [rbp+arg_10], 0
0x1800020f6  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x1800020fc  mov     ebx, eax
0x1800020fe  test    eax, eax
0x180002100  js      short loc_18000217E
0x180002102  lea     rdx, [rbp+arg_10]; struct DirectUI::Element **
0x180002106  mov     rcx, rdi; this
0x180002109  call    ?_CreateConsentPopup@CEASConsentPopup@@AEAAJPEAPEAVElement@DirectUI@@@Z; CEASConsentPopup::_CreateConsentPopup(DirectUI::Element * *)
0x18000210e  mov     ebx, eax
0x180002110  test    eax, eax
0x180002112  js      short loc_18000216D
0x180002114  mov     rcx, [rdi+20h]
0x180002118  mov     rax, [rcx]
0x18000211b  mov     rax, [rax+110h]
0x180002122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002127  mov     ebx, eax
0x180002129  test    eax, eax
0x18000212b  js      short loc_18000216D
0x18000212d  xorps   xmm0, xmm0
0x180002130  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x180002134  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x180002138  movups  xmmword ptr [rbp+Msg.time], xmm0
0x18000213c  jmp     short loc_180002152
0x18000213e  lea     rcx, [rbp+Msg]; lpMsg
0x180002142  call    cs:__imp_TranslateMessage
0x180002148  lea     rcx, [rbp+Msg]; lpMsg
0x18000214c  call    cs:__imp_DispatchMessageW
0x180002152  xor     r9d, r9d; wMsgFilterMax
0x180002155  lea     rcx, [rbp+Msg]; lpMsg
0x180002159  xor     r8d, r8d; wMsgFilterMin
0x18000215c  xor     edx, edx; hWnd
0x18000215e  call    cs:__imp_GetMessageW
0x180002164  test    eax, eax
0x180002166  jnz     short loc_18000213E
0x180002168  mov     eax, [rdi+18h]
0x18000216b  mov     [rsi], eax
0x18000216d  mov     rcx, [rbp+arg_10]
0x180002171  test    rcx, rcx
0x180002174  jz      short loc_18000217E
0x180002176  mov     dl, 1
0x180002178  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18000217e  mov     rcx, [rbp+arg_8]
0x180002182  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x180002188  call    cs:__imp_UnInitThread
0x18000218e  lea     rcx, cs:180000000h
0x180002195  call    cs:__imp_UnInitProcessPriv
0x18000219b  mov     eax, ebx
0x18000219d  mov     rbx, [rsp+60h+arg_0]
0x1800021a5  add     rsp, 60h
0x1800021a9  pop     rdi
0x1800021aa  pop     rsi
0x1800021ab  pop     rbp
0x1800021ac  retn
```
