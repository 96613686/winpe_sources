# CW32System::CW32System(void)

- ea: `0x18002684c`
- end: `0x1800269ae`
- name: `??0CW32System@@QEAA@XZ`
- size: `354`
- prototype: `CW32System *__fastcall(CW32System *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180026f28`

## callees

- `0x18002684c`
- `0x180043e3c`
- `0x180048030`

## import_xrefs

- `KERNEL32!GetACP` at `0x1800268a2`
- `KERNEL32!GetACP` at `0x1800268a2`
- `KERNEL32!GetSystemDefaultLCID` at `0x180026890`
- `KERNEL32!GetSystemDefaultLCID` at `0x180026890`
- `USER32!RegisterWindowMessageA` at `0x1800268d5`
- `USER32!RegisterWindowMessageA` at `0x1800268ee`
- `USER32!RegisterWindowMessageA` at `0x180026907`
- `USER32!RegisterWindowMessageA` at `0x180026920`
- `USER32!RegisterWindowMessageA` at `0x180026939`
- `USER32!RegisterWindowMessageA` at `0x180026979`
- `USER32!RegisterWindowMessageA` at `0x180026992`
- `USER32!RegisterWindowMessageA` at `0x1800268d5`
- `USER32!RegisterWindowMessageA` at `0x1800268ee`
- `USER32!RegisterWindowMessageA` at `0x180026907`
- `USER32!RegisterWindowMessageA` at `0x180026920`
- `USER32!RegisterWindowMessageA` at `0x180026939`
- `USER32!RegisterWindowMessageA` at `0x180026979`
- `USER32!RegisterWindowMessageA` at `0x180026992`

## string_xrefs

- `0x180026913`: `MSIMEQueryPosition`
- `0x180026985`: `MSIMEReconvertRequest`
- `0x1800268e1`: `MSIMEMouseOperation`
- `0x1800268fa`: `MSIMEDocumentFeed`
- `0x180026972`: `MSIMEReconvert`
- `0x18002692c`: `MSIMEService`

## pseudocode

```c
CW32System *__fastcall CW32System::CW32System(CW32System *this, unsigned int *a2, unsigned int *a3)
{
  UINT v4; // eax

  if ( (unsigned int)CW32System::GetVersion((unsigned int *)this, a2, a3) )
  {
    CW32System::_fHaveAIMM = 0;
    CW32System::_pIMEShare = 0;
    CW32System::_icr3DDarkShadow = 6;
    if ( CW32System::_dwMajorVersion >= 4 )
      CW32System::_icr3DDarkShadow = 21;
  }
  CW32System::_syslcid = GetSystemDefaultLCID();
  CW32System::_ACP = GetACP();
  CW32System::_fCheckExe = 0;
  CW32System::_fSkipObjectData = 0;
  CThreadData::OnW32Init();
  CW32System::_fOleinitCheckDisabled = 0;
  CW32System::_MSMouseRoller = RegisterWindowMessageA("MSWHEEL_ROLLMSG");
  CW32System::_MSIMEMouseMsg = RegisterWindowMessageA("MSIMEMouseOperation");
  CW32System::_MSIMEDocFeedMsg = RegisterWindowMessageA("MSIMEDocumentFeed");
  CW32System::_MSIMEQueryPositionMsg = RegisterWindowMessageA("MSIMEQueryPosition");
  CW32System::_MSIMEServiceMsg = RegisterWindowMessageA("MSIMEService");
  if ( CW32System::_dwPlatformId == 1 || CW32System::_dwPlatformId == 2 && CW32System::_dwMajorVersion <= 4 )
  {
    CW32System::_MSIMEReconvertMsg = RegisterWindowMessageA("MSIMEReconvert");
    v4 = RegisterWindowMessageA("MSIMEReconvertRequest");
  }
  else
  {
    CW32System::_MSIMEReconvertMsg = 0;
    v4 = 0;
  }
  CW32System::_MSIMEReconvertRequestMsg = v4;
  return this;
}

```

## disassembly

```asm
0x18002684c  push    rbx
0x18002684e  sub     rsp, 20h
0x180026852  mov     rbx, rcx
0x180026855  call    ?GetVersion@CW32System@@SAHPEAK00@Z; CW32System::GetVersion(ulong *,ulong *,ulong *)
0x18002685a  test    eax, eax
0x18002685c  jz      short loc_180026890
0x18002685e  cmp     cs:?_dwMajorVersion@CW32System@@2KA, 4; ulong CW32System::_dwMajorVersion
0x180026865  mov     cs:?_fHaveAIMM@CW32System@@2HA, 0; int CW32System::_fHaveAIMM
0x18002686f  mov     cs:?_pIMEShare@CW32System@@2PEAVCIMEShare@@EA, 0; CIMEShare * CW32System::_pIMEShare
0x18002687a  mov     cs:?_icr3DDarkShadow@CW32System@@2HA, 6; int CW32System::_icr3DDarkShadow
0x180026884  jb      short loc_180026890
0x180026886  mov     cs:?_icr3DDarkShadow@CW32System@@2HA, 15h; int CW32System::_icr3DDarkShadow
0x180026890  call    cs:__imp_GetSystemDefaultLCID
0x180026897  nop     dword ptr [rax+rax+00h]
0x18002689c  mov     cs:?_syslcid@CW32System@@0KA, eax; ulong CW32System::_syslcid
0x1800268a2  call    cs:__imp_GetACP
0x1800268a9  nop     dword ptr [rax+rax+00h]
0x1800268ae  mov     cs:?_ACP@CW32System@@0IA, eax; uint CW32System::_ACP
0x1800268b4  mov     cs:?_fCheckExe@CW32System@@2EA, 0; uchar CW32System::_fCheckExe
0x1800268bb  mov     cs:?_fSkipObjectData@CW32System@@2EA, 0; uchar CW32System::_fSkipObjectData
0x1800268c2  call    ?OnW32Init@CThreadData@@SAXXZ; CThreadData::OnW32Init(void)
0x1800268c7  lea     rcx, String; "MSWHEEL_ROLLMSG"
0x1800268ce  mov     cs:?_fOleinitCheckDisabled@CW32System@@2_NA, 0; bool CW32System::_fOleinitCheckDisabled
0x1800268d5  call    cs:__imp_RegisterWindowMessageA
0x1800268dc  nop     dword ptr [rax+rax+00h]
0x1800268e1  lea     rcx, aMsimemouseoper; "MSIMEMouseOperation"
0x1800268e8  mov     cs:?_MSMouseRoller@CW32System@@2IA, eax; uint CW32System::_MSMouseRoller
0x1800268ee  call    cs:__imp_RegisterWindowMessageA
0x1800268f5  nop     dword ptr [rax+rax+00h]
0x1800268fa  lea     rcx, aMsimedocumentf; "MSIMEDocumentFeed"
0x180026901  mov     cs:?_MSIMEMouseMsg@CW32System@@2IA, eax; uint CW32System::_MSIMEMouseMsg
0x180026907  call    cs:__imp_RegisterWindowMessageA
0x18002690e  nop     dword ptr [rax+rax+00h]
0x180026913  lea     rcx, aMsimequeryposi; "MSIMEQueryPosition"
0x18002691a  mov     cs:?_MSIMEDocFeedMsg@CW32System@@2IA, eax; uint CW32System::_MSIMEDocFeedMsg
0x180026920  call    cs:__imp_RegisterWindowMessageA
0x180026927  nop     dword ptr [rax+rax+00h]
0x18002692c  lea     rcx, aMsimeservice; "MSIMEService"
0x180026933  mov     cs:?_MSIMEQueryPositionMsg@CW32System@@2IA, eax; uint CW32System::_MSIMEQueryPositionMsg
0x180026939  call    cs:__imp_RegisterWindowMessageA
0x180026940  nop     dword ptr [rax+rax+00h]
0x180026945  mov     cs:?_MSIMEServiceMsg@CW32System@@2IA, eax; uint CW32System::_MSIMEServiceMsg
0x18002694b  mov     eax, cs:?_dwPlatformId@CW32System@@0KA; ulong CW32System::_dwPlatformId
0x180026951  cmp     eax, 1
0x180026954  jz      short loc_180026972
0x180026956  cmp     eax, 2
0x180026959  jnz     short loc_180026964
0x18002695b  cmp     cs:?_dwMajorVersion@CW32System@@2KA, 4; ulong CW32System::_dwMajorVersion
0x180026962  jbe     short loc_180026972
0x180026964  mov     cs:?_MSIMEReconvertMsg@CW32System@@2IA, 0; uint CW32System::_MSIMEReconvertMsg
0x18002696e  xor     eax, eax
0x180026970  jmp     short loc_18002699E
0x180026972  lea     rcx, aMsimereconvert; "MSIMEReconvert"
0x180026979  call    cs:__imp_RegisterWindowMessageA
0x180026980  nop     dword ptr [rax+rax+00h]
0x180026985  lea     rcx, aMsimereconvert_0; "MSIMEReconvertRequest"
0x18002698c  mov     cs:?_MSIMEReconvertMsg@CW32System@@2IA, eax; uint CW32System::_MSIMEReconvertMsg
0x180026992  call    cs:__imp_RegisterWindowMessageA
0x180026999  nop     dword ptr [rax+rax+00h]
0x18002699e  mov     cs:?_MSIMEReconvertRequestMsg@CW32System@@2IA, eax; uint CW32System::_MSIMEReconvertRequestMsg
0x1800269a4  mov     rax, rbx
0x1800269a7  add     rsp, 20h
0x1800269ab  pop     rbx
0x1800269ac  retn
```
