# CW32System::CW32System(void)

- ea: `0x180023468`
- end: `0x1800235e7`
- name: `??0CW32System@@QEAA@XZ`
- size: `383`
- prototype: `CW32System *__fastcall(CW32System *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x180022d48`

## callees

- `0x180023468`
- `0x180046fa4`

## import_xrefs

- `KERNEL32!GetACP` at `0x1800234b8`
- `KERNEL32!GetACP` at `0x1800234b8`
- `KERNEL32!TlsAlloc` at `0x1800234d2`
- `KERNEL32!TlsAlloc` at `0x1800234d2`
- `KERNEL32!GetSystemDefaultLCID` at `0x1800234ac`
- `KERNEL32!GetSystemDefaultLCID` at `0x1800234ac`
- `KERNEL32!GetProcessHeap` at `0x1800234ea`
- `KERNEL32!GetProcessHeap` at `0x1800234ea`
- `KERNEL32!HeapAlloc` at `0x180023507`
- `KERNEL32!HeapAlloc` at `0x180023507`
- `USER32!RegisterWindowMessageA` at `0x180023539`
- `USER32!RegisterWindowMessageA` at `0x18002354c`
- `USER32!RegisterWindowMessageA` at `0x18002355f`
- `USER32!RegisterWindowMessageA` at `0x180023572`
- `USER32!RegisterWindowMessageA` at `0x180023585`
- `USER32!RegisterWindowMessageA` at `0x1800235bf`
- `USER32!RegisterWindowMessageA` at `0x1800235d2`
- `USER32!RegisterWindowMessageA` at `0x180023539`
- `USER32!RegisterWindowMessageA` at `0x18002354c`
- `USER32!RegisterWindowMessageA` at `0x18002355f`
- `USER32!RegisterWindowMessageA` at `0x180023572`
- `USER32!RegisterWindowMessageA` at `0x180023585`
- `USER32!RegisterWindowMessageA` at `0x1800235bf`
- `USER32!RegisterWindowMessageA` at `0x1800235d2`

## string_xrefs

- `0x180023565`: `MSIMEQueryPosition`
- `0x1800235c5`: `MSIMEReconvertRequest`
- `0x18002353f`: `MSIMEMouseOperation`
- `0x180023552`: `MSIMEDocumentFeed`
- `0x1800235b8`: `MSIMEReconvert`
- `0x180023578`: `MSIMEService`

## pseudocode

```c
CW32System *__fastcall CW32System::CW32System(CW32System *this, unsigned int *a2, unsigned int *a3)
{
  HANDLE ProcessHeap; // rax
  struct CThreadData *v5; // rax
  UINT v6; // eax

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
  CThreadData::_dwTlsIndex = TlsAlloc();
  ProcessHeap = g_hHeap;
  if ( (g_hHeap || (ProcessHeap = GetProcessHeap(), (g_hHeap = ProcessHeap) != 0))
    && (v5 = (struct CThreadData *)HeapAlloc(ProcessHeap, 8u, 8u)) != 0 )
  {
    *(_DWORD *)v5 = 0;
    *((_BYTE *)v5 + 4) = 0;
  }
  else
  {
    v5 = 0;
  }
  CW32System::_pNotCountingSingleton = v5;
  *((_BYTE *)v5 + 5) = 1;
  CW32System::_fOleinitCheckDisabled = 0;
  CW32System::_MSMouseRoller = RegisterWindowMessageA("MSWHEEL_ROLLMSG");
  CW32System::_MSIMEMouseMsg = RegisterWindowMessageA("MSIMEMouseOperation");
  CW32System::_MSIMEDocFeedMsg = RegisterWindowMessageA("MSIMEDocumentFeed");
  CW32System::_MSIMEQueryPositionMsg = RegisterWindowMessageA("MSIMEQueryPosition");
  CW32System::_MSIMEServiceMsg = RegisterWindowMessageA("MSIMEService");
  if ( CW32System::_dwPlatformId == 1 || CW32System::_dwPlatformId == 2 && CW32System::_dwMajorVersion <= 4 )
  {
    CW32System::_MSIMEReconvertMsg = RegisterWindowMessageA("MSIMEReconvert");
    v6 = RegisterWindowMessageA("MSIMEReconvertRequest");
  }
  else
  {
    CW32System::_MSIMEReconvertMsg = 0;
    v6 = 0;
  }
  CW32System::_MSIMEReconvertRequestMsg = v6;
  return this;
}

```

## disassembly

```asm
0x180023468  push    rbx
0x18002346a  sub     rsp, 20h
0x18002346e  mov     rbx, rcx
0x180023471  call    ?GetVersion@CW32System@@SAHPEAK00@Z; CW32System::GetVersion(ulong *,ulong *,ulong *)
0x180023476  test    eax, eax
0x180023478  jz      short loc_1800234AC
0x18002347a  cmp     cs:?_dwMajorVersion@CW32System@@2KA, 4; ulong CW32System::_dwMajorVersion
0x180023481  mov     cs:?_fHaveAIMM@CW32System@@2HA, 0; int CW32System::_fHaveAIMM
0x18002348b  mov     cs:?_pIMEShare@CW32System@@2PEAVCIMEShare@@EA, 0; CIMEShare * CW32System::_pIMEShare
0x180023496  mov     cs:?_icr3DDarkShadow@CW32System@@2HA, 6; int CW32System::_icr3DDarkShadow
0x1800234a0  jb      short loc_1800234AC
0x1800234a2  mov     cs:?_icr3DDarkShadow@CW32System@@2HA, 15h; int CW32System::_icr3DDarkShadow
0x1800234ac  call    cs:__imp_GetSystemDefaultLCID
0x1800234b2  mov     cs:?_syslcid@CW32System@@0KA, eax; ulong CW32System::_syslcid
0x1800234b8  call    cs:__imp_GetACP
0x1800234be  mov     cs:?_ACP@CW32System@@0IA, eax; uint CW32System::_ACP
0x1800234c4  mov     cs:?_fCheckExe@CW32System@@2EA, 0; uchar CW32System::_fCheckExe
0x1800234cb  mov     cs:?_fSkipObjectData@CW32System@@2EA, 0; uchar CW32System::_fSkipObjectData
0x1800234d2  call    cs:__imp_TlsAlloc
0x1800234d8  mov     cs:?_dwTlsIndex@CThreadData@@0KA, eax; ulong CThreadData::_dwTlsIndex
0x1800234de  mov     rax, cs:?g_hHeap@@3PEAXEA; void * g_hHeap
0x1800234e5  test    rax, rax
0x1800234e8  jnz     short loc_1800234FC
0x1800234ea  call    cs:__imp_GetProcessHeap
0x1800234f0  mov     cs:?g_hHeap@@3PEAXEA, rax; void * g_hHeap
0x1800234f7  test    rax, rax
0x1800234fa  jz      short loc_18002351E
0x1800234fc  mov     edx, 8; dwFlags
0x180023501  mov     rcx, rax; hHeap
0x180023504  mov     r8d, edx; dwBytes
0x180023507  call    cs:__imp_HeapAlloc
0x18002350d  test    rax, rax
0x180023510  jz      short loc_18002351E
0x180023512  mov     dword ptr [rax], 0
0x180023518  mov     byte ptr [rax+4], 0
0x18002351c  jmp     short loc_180023520
0x18002351e  xor     eax, eax
0x180023520  lea     rcx, String; "MSWHEEL_ROLLMSG"
0x180023527  mov     cs:?_pNotCountingSingleton@CW32System@@2PEAVCThreadData@@EA, rax; CThreadData * CW32System::_pNotCountingSingleton
0x18002352e  mov     byte ptr [rax+5], 1
0x180023532  mov     cs:?_fOleinitCheckDisabled@CW32System@@2_NA, 0; bool CW32System::_fOleinitCheckDisabled
0x180023539  call    cs:__imp_RegisterWindowMessageA
0x18002353f  lea     rcx, aMsimemouseoper; "MSIMEMouseOperation"
0x180023546  mov     cs:?_MSMouseRoller@CW32System@@2IA, eax; uint CW32System::_MSMouseRoller
0x18002354c  call    cs:__imp_RegisterWindowMessageA
0x180023552  lea     rcx, aMsimedocumentf; "MSIMEDocumentFeed"
0x180023559  mov     cs:?_MSIMEMouseMsg@CW32System@@2IA, eax; uint CW32System::_MSIMEMouseMsg
0x18002355f  call    cs:__imp_RegisterWindowMessageA
0x180023565  lea     rcx, aMsimequeryposi; "MSIMEQueryPosition"
0x18002356c  mov     cs:?_MSIMEDocFeedMsg@CW32System@@2IA, eax; uint CW32System::_MSIMEDocFeedMsg
0x180023572  call    cs:__imp_RegisterWindowMessageA
0x180023578  lea     rcx, aMsimeservice; "MSIMEService"
0x18002357f  mov     cs:?_MSIMEQueryPositionMsg@CW32System@@2IA, eax; uint CW32System::_MSIMEQueryPositionMsg
0x180023585  call    cs:__imp_RegisterWindowMessageA
0x18002358b  mov     cs:?_MSIMEServiceMsg@CW32System@@2IA, eax; uint CW32System::_MSIMEServiceMsg
0x180023591  mov     eax, cs:?_dwPlatformId@CW32System@@0KA; ulong CW32System::_dwPlatformId
0x180023597  cmp     eax, 1
0x18002359a  jz      short loc_1800235B8
0x18002359c  cmp     eax, 2
0x18002359f  jnz     short loc_1800235AA
0x1800235a1  cmp     cs:?_dwMajorVersion@CW32System@@2KA, 4; ulong CW32System::_dwMajorVersion
0x1800235a8  jbe     short loc_1800235B8
0x1800235aa  mov     cs:?_MSIMEReconvertMsg@CW32System@@2IA, 0; uint CW32System::_MSIMEReconvertMsg
0x1800235b4  xor     eax, eax
0x1800235b6  jmp     short loc_1800235D8
0x1800235b8  lea     rcx, aMsimereconvert; "MSIMEReconvert"
0x1800235bf  call    cs:__imp_RegisterWindowMessageA
0x1800235c5  lea     rcx, aMsimereconvert_0; "MSIMEReconvertRequest"
0x1800235cc  mov     cs:?_MSIMEReconvertMsg@CW32System@@2IA, eax; uint CW32System::_MSIMEReconvertMsg
0x1800235d2  call    cs:__imp_RegisterWindowMessageA
0x1800235d8  mov     cs:?_MSIMEReconvertRequestMsg@CW32System@@2IA, eax; uint CW32System::_MSIMEReconvertRequestMsg
0x1800235de  mov     rax, rbx
0x1800235e1  add     rsp, 20h
0x1800235e5  pop     rbx
0x1800235e6  retn
```
