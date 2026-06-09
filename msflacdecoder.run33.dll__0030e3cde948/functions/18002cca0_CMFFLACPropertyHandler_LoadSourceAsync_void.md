# CMFFLACPropertyHandler::LoadSourceAsync(void)

- ea: `0x18002cca0`
- end: `0x18002cdaf`
- name: `?LoadSourceAsync@CMFFLACPropertyHandler@@AEAAJXZ`
- size: `271`
- prototype: `__int64 __fastcall(CMFFLACPropertyHandler *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002cb30`

## callees

- `0x180016e48`
- `0x180020398`
- `0x180020484`
- `0x180021588`
- `0x1800221ec`
- `0x18002cca0`

## import_xrefs

- `MFPlat!MFCreateMFByteStreamOnStream` at `0x18002cd01`
- `MFPlat!MFCreateMFByteStreamOnStream` at `0x18002cd01`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMFFLACPropertyHandler::LoadSourceAsync(CMFFLACPropertyHandler *this)
{
  struct CFLACSource **v2; // rsi
  HRESULT Instance; // ebx
  __int64 v4; // rdx
  struct IUnknown *v5; // r9
  int v7; // [rsp+60h] [rbp+20h]
  IMFByteStream *ppByteStream; // [rsp+68h] [rbp+28h] BYREF

  ppByteStream = 0;
  v2 = (struct CFLACSource **)((char *)this + 1936);
  if ( *((_QWORD *)this + 242) )
  {
    Instance = -1072875845;
    v7 = -1072875845;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v4 = 55;
LABEL_13:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v4,
        &WPP_36e4e3a47ce73e52b63ec011625d5c06_Traceguids,
        this,
        Instance);
      Instance = v7;
    }
  }
  else
  {
    Instance = MFCreateMFByteStreamOnStream(*((IStream **)this + 111), &ppByteStream);
    v7 = Instance;
    if ( Instance >= 0 )
    {
      Instance = CFLACSource::CreateInstance(v2);
      v7 = Instance;
      if ( Instance >= 0 )
      {
        *((_BYTE *)*v2 + 389) |= 8u;
        Instance = CFLACSource::BeginOpen(*v2, ppByteStream, (struct IMFAsyncCallback *)this + 241, v5);
        v7 = Instance;
        if ( Instance < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v4 = 58;
          goto LABEL_13;
        }
      }
      else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v4 = 57;
        goto LABEL_13;
      }
    }
    else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v4 = 56;
      goto LABEL_13;
    }
  }
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&ppByteStream);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18002cca0  mov     [rsp-18h+arg_10], rbx
0x18002cca5  push    rbp
0x18002cca6  push    rsi
0x18002cca7  push    rdi
0x18002cca8  mov     rbp, rsp
0x18002ccab  sub     rsp, 40h
0x18002ccaf  mov     rdi, rcx
0x18002ccb2  mov     [rbp+arg_0], 0
0x18002ccb9  mov     [rbp+var_10], rcx
0x18002ccbd  lea     rax, [rbp+arg_0]
0x18002ccc1  mov     [rbp+var_8], rax
0x18002ccc5  mov     [rbp+ppByteStream], 0
0x18002cccd  lea     rsi, [rcx+790h]
0x18002ccd4  cmp     qword ptr [rsi], 0
0x18002ccd8  jz      short loc_18002CCF6
0x18002ccda  mov     ebx, 0C00D36BBh
0x18002ccdf  mov     [rbp+arg_0], ebx
0x18002cce2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002cce7  cmp     al, 1
0x18002cce9  jb      loc_18002CD96
0x18002ccef  mov     edx, 37h ; '7'
0x18002ccf4  jmp     short loc_18002CD75
0x18002ccf6  lea     rdx, [rbp+ppByteStream]; ppByteStream
0x18002ccfa  mov     rcx, [rcx+378h]; pStream
0x18002cd01  call    cs:__imp_MFCreateMFByteStreamOnStream
0x18002cd07  mov     ebx, eax
0x18002cd09  mov     [rbp+arg_0], eax
0x18002cd0c  test    eax, eax
0x18002cd0e  jns     short loc_18002CD20
0x18002cd10  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002cd15  cmp     al, 1
0x18002cd17  jb      short loc_18002CD96
0x18002cd19  mov     edx, 38h ; '8'
0x18002cd1e  jmp     short loc_18002CD75
0x18002cd20  mov     rcx, rsi; struct CFLACSource **
0x18002cd23  call    ?CreateInstance@CFLACSource@@SAJPEAPEAV1@@Z; CFLACSource::CreateInstance(CFLACSource * *)
0x18002cd28  mov     ebx, eax
0x18002cd2a  mov     [rbp+arg_0], eax
0x18002cd2d  test    eax, eax
0x18002cd2f  jns     short loc_18002CD41
0x18002cd31  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002cd36  cmp     al, 1
0x18002cd38  jb      short loc_18002CD96
0x18002cd3a  mov     edx, 39h ; '9'
0x18002cd3f  jmp     short loc_18002CD75
0x18002cd41  mov     rax, [rsi]
0x18002cd44  or      byte ptr [rax+185h], 8
0x18002cd4b  lea     r8, [rdi+788h]; struct IMFAsyncCallback *
0x18002cd52  mov     rdx, [rbp+ppByteStream]; struct IMFByteStream *
0x18002cd56  mov     rcx, [rsi]; this
0x18002cd59  call    ?BeginOpen@CFLACSource@@QEAAJPEAUIMFByteStream@@PEAUIMFAsyncCallback@@PEAUIUnknown@@@Z; CFLACSource::BeginOpen(IMFByteStream *,IMFAsyncCallback *,IUnknown *)
0x18002cd5e  mov     ebx, eax
0x18002cd60  mov     [rbp+arg_0], eax
0x18002cd63  test    eax, eax
0x18002cd65  jns     short loc_18002CD96
0x18002cd67  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002cd6c  cmp     al, 1
0x18002cd6e  jb      short loc_18002CD96
0x18002cd70  mov     edx, 3Ah ; ':'
0x18002cd75  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cd7c  mov     [rsp+40h+var_20], ebx
0x18002cd80  mov     r9, rdi
0x18002cd83  lea     r8, WPP_36e4e3a47ce73e52b63ec011625d5c06_Traceguids
0x18002cd8a  mov     rcx, [rcx+10h]
0x18002cd8e  call    WPP_SF_qd
0x18002cd93  mov     ebx, [rbp+arg_0]
0x18002cd96  lea     rcx, [rbp+ppByteStream]
0x18002cd9a  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x18002cd9f  nop
0x18002cda0  mov     eax, ebx
0x18002cda2  mov     rbx, [rsp+40h+arg_10]
0x18002cda7  add     rsp, 40h
0x18002cdab  pop     rdi
0x18002cdac  pop     rsi
0x18002cdad  pop     rbp
0x18002cdae  retn
```
