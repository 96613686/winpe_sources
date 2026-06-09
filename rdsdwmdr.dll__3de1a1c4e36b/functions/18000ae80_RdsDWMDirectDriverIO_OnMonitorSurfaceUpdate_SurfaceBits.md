# RdsDWMDirectDriverIO::OnMonitorSurfaceUpdate(_SurfaceBits *)

- ea: `0x18000ae80`
- end: `0x18000b2d9`
- name: `?OnMonitorSurfaceUpdate@RdsDWMDirectDriverIO@@UEAAJPEAU_SurfaceBits@@@Z`
- size: `1113`
- prototype: `__int64 __fastcall(RdsDWMDirectDriverIO *__hidden this, struct _SurfaceBits *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callees

- `0x1800010f8`
- `0x180001724`
- `0x1800021f0`
- `0x1800032d4`
- `0x180003314`
- `0x180004130`
- `0x180004248`
- `0x180005f20`
- `0x1800083a0`
- `0x18000ae80`
- `0x18000bdbc`
- `0x18002b922`

## string_xrefs

- `0x18000aef9`: `Failed to allocate new Ioctl RDPIDD_OPCODE_RAIL_MONITOR_SURFACE_UPDATE`
- `0x18000af12`: `OnMonitorSurfaceUpdate`
- `0x18000b0c4`: `OnMonitorSurfaceUpdate`
- `0x18000b250`: `OnMonitorSurfaceUpdate`
- `0x18000afc3`: `Sending monitor surface update (abs(height = %d), width = %d, TargetId = %d)`
- `0x18000b1d2`: `pSourceImage->CopyFrom failed`
- `0x18000b237`: `SendToRemoteDriver:Failed to send RDPIDD_OPCODE_MONITOR_SURFACE_UPDATE Ioctl`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectDriverIO::OnMonitorSurfaceUpdate(RdsDWMDirectDriverIO *this, struct _SurfaceBits *a2)
{
  RdsDWMDirectDriverIO *v2; // r14
  char *v4; // rbx
  int v5; // eax
  unsigned int v6; // esi
  int v7; // r15d
  char *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // edi
  int v13; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  const char *v16; // rax
  __int16 *v17; // rdx
  int v18; // r9d
  int v19; // eax
  __int64 v20; // r8
  __int64 v21; // r9
  unsigned __int8 *v23; // [rsp+20h] [rbp-69h]
  int v24; // [rsp+38h] [rbp-51h]
  int v25; // [rsp+38h] [rbp-51h]
  int v26; // [rsp+40h] [rbp-49h]
  int v27; // [rsp+40h] [rbp-49h]
  int v28; // [rsp+48h] [rbp-41h]
  int v29; // [rsp+50h] [rbp-39h]
  const char *v30; // [rsp+60h] [rbp-29h] BYREF
  const char *v31; // [rsp+68h] [rbp-21h] BYREF
  unsigned __int8 v32[8]; // [rsp+70h] [rbp-19h] BYREF
  _QWORD v33[2]; // [rsp+78h] [rbp-11h] BYREF
  __int128 v34; // [rsp+88h] [rbp-1h]
  _QWORD v35[2]; // [rsp+98h] [rbp+Fh] BYREF
  __int128 v36; // [rsp+A8h] [rbp+1Fh]
  const char *v37; // [rsp+F0h] [rbp+67h] BYREF
  int v38; // [rsp+100h] [rbp+77h] BYREF
  const char *v39; // [rsp+108h] [rbp+7Fh] BYREF

  v2 = (RdsDWMDirectDriverIO *)((char *)this - 48);
  if ( !*((_DWORD *)this + 146) )
  {
    v4 = 0;
    if ( *((_QWORD *)this + 68) == -1 )
      goto LABEL_31;
  }
  v5 = -*((_DWORD *)a2 + 7);
  if ( *((int *)a2 + 7) > 0 )
    v5 = *((_DWORD *)a2 + 7);
  v6 = 4 * *((_DWORD *)a2 + 6) * v5;
  v7 = v6 + 32;
  v8 = (char *)operator new(v6 + 32);
  v4 = v8;
  if ( v8 )
  {
    *(_DWORD *)v8 = v7;
    *((_DWORD *)v8 + 2) = 513;
    *(_QWORD *)(v8 + 12) = *(_QWORD *)a2;
    *((_DWORD *)v8 + 5) = *((_DWORD *)a2 + 2);
    v13 = -*((_DWORD *)a2 + 7);
    if ( *((int *)a2 + 7) > 0 )
      v13 = *((_DWORD *)a2 + 7);
    *((_DWORD *)v4 + 7) = v13;
    *((_DWORD *)v4 + 6) = *((_DWORD *)a2 + 6);
    if ( (unsigned int)dword_180044008 > 5 )
    {
      LODWORD(v37) = *((_DWORD *)a2 + 2);
      v38 = *((_DWORD *)a2 + 6);
      LODWORD(v39) = *((_DWORD *)a2 + 7);
      *(_QWORD *)v32 = "Sending monitor surface update (abs(height = %d), width = %d, TargetId = %d)";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (__int64)&dword_180037D94,
        v10,
        v11,
        (const unsigned __int16 **)v32,
        (__int64)&v39,
        (__int64)&v38,
        (__int64)&v37);
    }
    if ( *((int *)a2 + 7) <= 0 )
    {
      memcpy_0(v4 + 32, *((const void **)a2 + 2), v6);
    }
    else
    {
      if ( (unsigned int)dword_180044008 > 5 )
      {
        v37 = "Height is flipped so reverse the bitmap";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v9,
          (__int64)byte_180037D6B,
          v10,
          v11,
          (const unsigned __int16 **)&v37);
      }
      v29 = *((_DWORD *)a2 + 7);
      v28 = *((_DWORD *)a2 + 6);
      v33[0] = 0;
      v33[1] = 0;
      v34 = 0;
      v35[0] = 0;
      v35[1] = 0;
      v36 = 0;
      if ( !PixelMap::Attach(
              (PixelMap *)v35,
              (unsigned __int8 *)v4 + 32,
              v6,
              v28,
              v29,
              4 * v28,
              0x20u,
              v24,
              v26,
              v28,
              v29) )
      {
        v12 = -2147024809;
        if ( (unsigned int)dword_180044008 <= 2 )
        {
LABEL_19:
          PixelMap::~PixelMap((PixelMap *)v35);
          PixelMap::~PixelMap((PixelMap *)v33);
          goto LABEL_32;
        }
        v16 = "destImage.Attach failed";
        LODWORD(v37) = 1348;
        v17 = &word_180037D16;
LABEL_18:
        v39 = v16;
        *(_QWORD *)v32 = "OnMonitorSurfaceUpdate";
        v31 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
        v30 = "Error condition failed";
        v38 = -2147024809;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          2147942487LL,
          (__int64)v17,
          v14,
          v15,
          (const unsigned __int16 **)&v30,
          (__int64)&v38,
          (const unsigned __int16 **)&v31,
          (__int64)&v37,
          (const unsigned __int16 **)v32,
          (const unsigned __int16 **)&v39);
        goto LABEL_19;
      }
      if ( !PixelMap::Attach(
              (PixelMap *)v33,
              *((unsigned __int8 **)a2 + 2),
              v6,
              *((_DWORD *)a2 + 6),
              *((_DWORD *)a2 + 7),
              4 * *((_DWORD *)a2 + 6),
              0x20u,
              v25,
              v27,
              *((_DWORD *)a2 + 6),
              *((_DWORD *)a2 + 7)) )
      {
        v12 = -2147024809;
        if ( (unsigned int)dword_180044008 <= 2 )
          goto LABEL_19;
        v16 = "image.Attach failed";
        LODWORD(v37) = 1355;
        v17 = (__int16 *)byte_180037CC1;
        goto LABEL_18;
      }
      PixelMap::RevertIteration((PixelMap *)v33);
      if ( !PixelMap::CopyFrom((PixelMap *)v35, (const struct PixelMap *)v33) )
      {
        v12 = -2147024809;
        if ( (unsigned int)dword_180044008 <= 2 )
          goto LABEL_19;
        v16 = "pSourceImage->CopyFrom failed";
        LODWORD(v37) = 1360;
        v17 = (__int16 *)&dword_180037C6C;
        goto LABEL_18;
      }
      PixelMap::~PixelMap((PixelMap *)v35);
      PixelMap::~PixelMap((PixelMap *)v33);
    }
    v19 = RdsDWMDirectDriverIO::SendToRemoteDriver(v2, v7, (unsigned __int8 *)v4, v18, v23);
    v12 = v19;
    if ( v19 < 0 )
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        LODWORD(v37) = 1368;
        v39 = "SendToRemoteDriver:Failed to send RDPIDD_OPCODE_MONITOR_SURFACE_UPDATE Ioctl";
        v38 = v19;
        *(_QWORD *)v32 = "OnMonitorSurfaceUpdate";
        v31 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
        v30 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)dword_180044008,
          (__int64)&byte_180037C17,
          v20,
          v21,
          (const unsigned __int16 **)&v30,
          (__int64)&v38,
          (const unsigned __int16 **)&v31,
          (__int64)&v37,
          (const unsigned __int16 **)v32,
          (const unsigned __int16 **)&v39);
      }
      goto LABEL_32;
    }
LABEL_31:
    v12 = 0;
    if ( !v4 )
      return v12;
LABEL_32:
    operator delete(v4);
    return v12;
  }
  v12 = -2147024882;
  if ( (unsigned int)dword_180044008 > 2 )
  {
    LODWORD(v37) = 1322;
    v39 = "Failed to allocate new Ioctl RDPIDD_OPCODE_RAIL_MONITOR_SURFACE_UPDATE";
    v38 = -2147024882;
    v30 = "OnMonitorSurfaceUpdate";
    v31 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
    *(_QWORD *)v32 = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v9,
      (__int64)&dword_180037DDC,
      v10,
      v11,
      (const unsigned __int16 **)v32,
      (__int64)&v38,
      (const unsigned __int16 **)&v31,
      (__int64)&v37,
      (const unsigned __int16 **)&v30,
      (const unsigned __int16 **)&v39);
  }
  return v12;
}

```

## disassembly

```asm
0x18000ae80  mov     [rsp-8+arg_8], rbx
0x18000ae85  push    rbp
0x18000ae86  push    rsi
0x18000ae87  push    rdi
0x18000ae88  push    r14
0x18000ae8a  push    r15
0x18000ae8c  lea     rbp, [rsp-37h]
0x18000ae91  sub     rsp, 0C0h
0x18000ae98  lea     r14, [rcx-30h]
0x18000ae9c  mov     rdi, rdx
0x18000ae9f  cmp     dword ptr [r14+278h], 0
0x18000aea7  jnz     short loc_18000AEB9
0x18000aea9  xor     ebx, ebx
0x18000aeab  cmp     qword ptr [rcx+220h], 0FFFFFFFFFFFFFFFFh
0x18000aeb3  jz      loc_18000B2B1
0x18000aeb9  mov     eax, [rdx+1Ch]
0x18000aebc  neg     eax
0x18000aebe  cmovs   eax, [rdx+1Ch]
0x18000aec2  imul    eax, [rdx+18h]
0x18000aec6  lea     esi, ds:0[rax*4]
0x18000aecd  lea     r15d, [rsi+20h]
0x18000aed1  mov     ecx, r15d; Size
0x18000aed4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000aed9  mov     rbx, rax
0x18000aedc  test    rax, rax
0x18000aedf  jnz     loc_18000AF76
0x18000aee5  mov     eax, cs:dword_180044008
0x18000aeeb  mov     edi, 8007000Eh
0x18000aef0  cmp     eax, 2
0x18000aef3  jbe     loc_18000B2C0
0x18000aef9  lea     rax, aFailedToAlloca_5; "Failed to allocate new Ioctl RDPIDD_OPC"...
0x18000af00  mov     dword ptr [rbp+57h+arg_0], 52Ah
0x18000af07  mov     [rbp+57h+arg_18], rax
0x18000af0b  lea     rdx, dword_180037DDC
0x18000af12  lea     rax, aOnmonitorsurfa; "OnMonitorSurfaceUpdate"
0x18000af19  mov     [rbp+57h+arg_10], edi
0x18000af1c  mov     [rbp+57h+var_80], rax
0x18000af20  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000af27  mov     [rbp+57h+var_78], rax
0x18000af2b  lea     rax, aErrorCondition; "Error condition failed"
0x18000af32  mov     qword ptr [rbp+57h+var_70], rax
0x18000af36  lea     rax, [rbp+57h+arg_18]
0x18000af3a  mov     qword ptr [rsp+0E0h+var_98], rax
0x18000af3f  lea     rax, [rbp+57h+var_80]
0x18000af43  mov     [rsp+0E0h+var_A0], rax
0x18000af48  lea     rax, [rbp+57h+arg_0]
0x18000af4c  mov     qword ptr [rsp+0E0h+var_A8], rax
0x18000af51  lea     rax, [rbp+57h+var_78]
0x18000af55  mov     qword ptr [rsp+0E0h+var_B0], rax
0x18000af5a  lea     rax, [rbp+57h+arg_10]
0x18000af5e  mov     qword ptr [rsp+0E0h+var_B8], rax
0x18000af63  lea     rax, [rbp+57h+var_70]
0x18000af67  mov     [rsp+0E0h+var_C0], rax
0x18000af6c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000af71  jmp     loc_18000B2C0
0x18000af76  mov     [rax], r15d
0x18000af79  mov     dword ptr [rax+8], 201h
0x18000af80  mov     rax, [rdi]
0x18000af83  mov     [rbx+0Ch], rax
0x18000af87  mov     eax, [rdi+8]
0x18000af8a  mov     [rbx+14h], eax
0x18000af8d  mov     eax, [rdi+1Ch]
0x18000af90  neg     eax
0x18000af92  cmovs   eax, [rdi+1Ch]
0x18000af96  mov     [rbx+1Ch], eax
0x18000af99  mov     eax, [rdi+18h]
0x18000af9c  mov     [rbx+18h], eax
0x18000af9f  mov     eax, cs:dword_180044008
0x18000afa5  cmp     eax, 5
0x18000afa8  jbe     short loc_18000AFF7
0x18000afaa  mov     eax, [rdi+8]
0x18000afad  lea     rdx, dword_180037D94
0x18000afb4  mov     dword ptr [rbp+57h+arg_0], eax
0x18000afb7  mov     eax, [rdi+18h]
0x18000afba  mov     [rbp+57h+arg_10], eax
0x18000afbd  mov     eax, [rdi+1Ch]
0x18000afc0  mov     dword ptr [rbp+57h+arg_18], eax
0x18000afc3  lea     rax, aSendingMonitor; "Sending monitor surface update (abs(hei"...
0x18000afca  mov     qword ptr [rbp+57h+var_70], rax
0x18000afce  lea     rax, [rbp+57h+arg_0]
0x18000afd2  mov     qword ptr [rsp+0E0h+var_A8], rax; int
0x18000afd7  lea     rax, [rbp+57h+arg_10]
0x18000afdb  mov     qword ptr [rsp+0E0h+var_B0], rax
0x18000afe0  lea     rax, [rbp+57h+arg_18]
0x18000afe4  mov     qword ptr [rsp+0E0h+var_B8], rax
0x18000afe9  lea     rax, [rbp+57h+var_70]
0x18000afed  mov     [rsp+0E0h+var_C0], rax; unsigned __int8 *
0x18000aff2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000aff7  cmp     dword ptr [rdi+1Ch], 0
0x18000affb  jle     loc_18000B200
0x18000b001  mov     eax, cs:dword_180044008
0x18000b007  cmp     eax, 5
0x18000b00a  jbe     short loc_18000B02C
0x18000b00c  lea     rax, aHeightIsFlippe; "Height is flipped so reverse the bitmap"
0x18000b013  mov     [rbp+57h+arg_0], rax
0x18000b017  lea     rdx, byte_180037D6B
0x18000b01e  lea     rax, [rbp+57h+arg_0]
0x18000b022  mov     [rsp+0E0h+var_C0], rax
0x18000b027  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000b02c  mov     ecx, [rdi+1Ch]
0x18000b02f  lea     rdx, [rbx+20h]; unsigned __int8 *
0x18000b033  mov     r9d, [rdi+18h]; int
0x18000b037  xorps   xmm0, xmm0
0x18000b03a  mov     [rsp+0E0h+var_90], ecx; int
0x18000b03e  mov     r8d, esi; int
0x18000b041  mov     [rsp+0E0h+var_98], r9d; int
0x18000b046  mov     [rsp+0E0h+var_B0], 20h ; ' '; unsigned int
0x18000b04e  lea     eax, ds:0[r9*4]
0x18000b056  mov     [rbp+57h+var_68], 0
0x18000b05e  mov     [rsp+0E0h+var_B8], eax; int
0x18000b062  mov     dword ptr [rsp+0E0h+var_C0], ecx; unsigned int
0x18000b066  lea     rcx, [rbp+57h+var_48]; this
0x18000b06a  mov     [rbp+57h+var_60], 0
0x18000b072  movdqu  [rbp+57h+var_58], xmm0
0x18000b077  mov     [rbp+57h+var_48], 0
0x18000b07f  mov     [rbp+57h+var_40], 0
0x18000b087  movdqu  [rbp+57h+var_38], xmm0
0x18000b08c  call    ?Attach@PixelMap@@QEAA_NPEAEHHHHHHHHH@Z; PixelMap::Attach(uchar *,int,int,int,int,int,int,int,int,int)
0x18000b091  test    al, al
0x18000b093  jnz     loc_18000B13A
0x18000b099  mov     eax, cs:dword_180044008
0x18000b09f  mov     ecx, 80070057h
0x18000b0a4  mov     edi, ecx
0x18000b0a6  cmp     eax, 2
0x18000b0a9  jbe     short loc_18000B123
0x18000b0ab  lea     rax, aDestimageAttac; "destImage.Attach failed"
0x18000b0b2  mov     dword ptr [rbp+57h+arg_0], 544h
0x18000b0b9  lea     rdx, word_180037D16
0x18000b0c0  mov     [rbp+57h+arg_18], rax
0x18000b0c4  lea     rax, aOnmonitorsurfa; "OnMonitorSurfaceUpdate"
0x18000b0cb  mov     qword ptr [rbp+57h+var_70], rax
0x18000b0cf  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000b0d6  mov     [rbp+57h+var_78], rax
0x18000b0da  lea     rax, aErrorCondition; "Error condition failed"
0x18000b0e1  mov     [rbp+57h+var_80], rax
0x18000b0e5  lea     rax, [rbp+57h+arg_18]
0x18000b0e9  mov     qword ptr [rsp+0E0h+var_98], rax
0x18000b0ee  lea     rax, [rbp+57h+var_70]
0x18000b0f2  mov     [rsp+0E0h+var_A0], rax
0x18000b0f7  lea     rax, [rbp+57h+arg_0]
0x18000b0fb  mov     qword ptr [rsp+0E0h+var_A8], rax
0x18000b100  lea     rax, [rbp+57h+var_78]
0x18000b104  mov     qword ptr [rsp+0E0h+var_B0], rax
0x18000b109  lea     rax, [rbp+57h+arg_10]
0x18000b10d  mov     qword ptr [rsp+0E0h+var_B8], rax
0x18000b112  lea     rax, [rbp+57h+var_80]
0x18000b116  mov     [rsp+0E0h+var_C0], rax
0x18000b11b  mov     [rbp+57h+arg_10], ecx
0x18000b11e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000b123  lea     rcx, [rbp+57h+var_48]; this
0x18000b127  call    ??1PixelMap@@QEAA@XZ; PixelMap::~PixelMap(void)
0x18000b12c  lea     rcx, [rbp+57h+var_68]; this
0x18000b130  call    ??1PixelMap@@QEAA@XZ; PixelMap::~PixelMap(void)
0x18000b135  jmp     loc_18000B2B8
0x18000b13a  mov     ecx, [rdi+1Ch]
0x18000b13d  mov     r8d, esi; int
0x18000b140  mov     r9d, [rdi+18h]; int
0x18000b144  mov     rdx, [rdi+10h]; unsigned __int8 *
0x18000b148  mov     [rsp+0E0h+var_90], ecx; int
0x18000b14c  mov     [rsp+0E0h+var_98], r9d; int
0x18000b151  lea     eax, ds:0[r9*4]
0x18000b159  mov     [rsp+0E0h+var_B0], 20h ; ' '; unsigned int
0x18000b161  mov     [rsp+0E0h+var_B8], eax; int
0x18000b165  mov     dword ptr [rsp+0E0h+var_C0], ecx; unsigned int
0x18000b169  lea     rcx, [rbp+57h+var_68]; this
0x18000b16d  call    ?Attach@PixelMap@@QEAA_NPEAEHHHHHHHHH@Z; PixelMap::Attach(uchar *,int,int,int,int,int,int,int,int,int)
0x18000b172  test    al, al
0x18000b174  jnz     short loc_18000B1A2
0x18000b176  mov     eax, cs:dword_180044008
0x18000b17c  mov     ecx, 80070057h
0x18000b181  mov     edi, ecx
0x18000b183  cmp     eax, 2
0x18000b186  jbe     short loc_18000B123
0x18000b188  lea     rax, aImageAttachFai; "image.Attach failed"
0x18000b18f  mov     dword ptr [rbp+57h+arg_0], 54Bh
0x18000b196  lea     rdx, byte_180037CC1
0x18000b19d  jmp     loc_18000B0C0
0x18000b1a2  lea     rcx, [rbp+57h+var_68]; this
0x18000b1a6  call    ?RevertIteration@PixelMap@@QEAAXXZ; PixelMap::RevertIteration(void)
0x18000b1ab  lea     rdx, [rbp+57h+var_68]; struct PixelMap *
0x18000b1af  lea     rcx, [rbp+57h+var_48]; this
0x18000b1b3  call    ?CopyFrom@PixelMap@@QEAA_NAEBV1@@Z; PixelMap::CopyFrom(PixelMap const &)
0x18000b1b8  test    al, al
0x18000b1ba  jnz     short loc_18000B1EC
0x18000b1bc  mov     eax, cs:dword_180044008
0x18000b1c2  mov     ecx, 80070057h
0x18000b1c7  mov     edi, ecx
0x18000b1c9  cmp     eax, 2
0x18000b1cc  jbe     loc_18000B123
0x18000b1d2  lea     rax, aPsourceimageCo; "pSourceImage->CopyFrom failed"
0x18000b1d9  mov     dword ptr [rbp+57h+arg_0], 550h
0x18000b1e0  lea     rdx, dword_180037C6C
0x18000b1e7  jmp     loc_18000B0C0
0x18000b1ec  lea     rcx, [rbp+57h+var_48]; this
0x18000b1f0  call    ??1PixelMap@@QEAA@XZ; PixelMap::~PixelMap(void)
0x18000b1f5  lea     rcx, [rbp+57h+var_68]; this
0x18000b1f9  call    ??1PixelMap@@QEAA@XZ; PixelMap::~PixelMap(void)
0x18000b1fe  jmp     short loc_18000B210
0x18000b200  mov     rdx, [rdi+10h]; Src
0x18000b204  lea     rcx, [rbx+20h]; void *
0x18000b208  mov     r8d, esi; Size
0x18000b20b  call    memcpy_0
0x18000b210  mov     r8, rbx; unsigned __int8 *
0x18000b213  mov     edx, r15d; int
0x18000b216  mov     rcx, r14; this
0x18000b219  call    ?SendToRemoteDriver@RdsDWMDirectDriverIO@@IEAAJHPEAEH0@Z; RdsDWMDirectDriverIO::SendToRemoteDriver(int,uchar *,int,uchar *)
0x18000b21e  mov     edi, eax
0x18000b220  test    eax, eax
0x18000b222  jns     loc_18000B2B1
0x18000b228  mov     ecx, cs:dword_180044008
0x18000b22e  cmp     ecx, 2
0x18000b231  jbe     loc_18000B2B8
0x18000b237  lea     rax, aSendtoremotedr_0; "SendToRemoteDriver:Failed to send RDPID"...
0x18000b23e  mov     dword ptr [rbp+57h+arg_0], 558h
0x18000b245  mov     [rbp+57h+arg_18], rax
0x18000b249  lea     rdx, byte_180037C17
0x18000b250  lea     rax, aOnmonitorsurfa; "OnMonitorSurfaceUpdate"
0x18000b257  mov     [rbp+57h+arg_10], edi
0x18000b25a  mov     qword ptr [rbp+57h+var_70], rax
0x18000b25e  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000b265  mov     [rbp+57h+var_78], rax
0x18000b269  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18000b270  mov     [rbp+57h+var_80], rax
0x18000b274  lea     rax, [rbp+57h+arg_18]
0x18000b278  mov     qword ptr [rsp+0E0h+var_98], rax
0x18000b27d  lea     rax, [rbp+57h+var_70]
0x18000b281  mov     [rsp+0E0h+var_A0], rax
0x18000b286  lea     rax, [rbp+57h+arg_0]
0x18000b28a  mov     qword ptr [rsp+0E0h+var_A8], rax
0x18000b28f  lea     rax, [rbp+57h+var_78]
0x18000b293  mov     qword ptr [rsp+0E0h+var_B0], rax
0x18000b298  lea     rax, [rbp+57h+arg_10]
0x18000b29c  mov     qword ptr [rsp+0E0h+var_B8], rax
0x18000b2a1  lea     rax, [rbp+57h+var_80]
0x18000b2a5  mov     [rsp+0E0h+var_C0], rax
0x18000b2aa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000b2af  jmp     short loc_18000B2B8
0x18000b2b1  xor     edi, edi
0x18000b2b3  test    rbx, rbx
0x18000b2b6  jz      short loc_18000B2C0
0x18000b2b8  mov     rcx, rbx; Block
0x18000b2bb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b2c0  mov     rbx, [rsp+0E0h+arg_8]
0x18000b2c8  mov     eax, edi
0x18000b2ca  add     rsp, 0C0h
0x18000b2d1  pop     r15
0x18000b2d3  pop     r14
0x18000b2d5  pop     rdi
0x18000b2d6  pop     rsi
0x18000b2d7  pop     rbp
0x18000b2d8  retn
```
