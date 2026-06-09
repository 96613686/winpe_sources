# InputServiceProxy::SendKeyboardEvent(KeyboardEvent const *,ulong)

- ea: `0x180172d00`
- end: `0x18017319d`
- name: `?SendKeyboardEvent@InputServiceProxy@@UEAAJPEBUKeyboardEvent@@K@Z`
- size: `1181`
- prototype: `__int64 __fastcall(InputServiceProxy *__hidden this, const struct KeyboardEvent *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180007b54`
- `0x180083d00`
- `0x18008dcac`
- `0x1800b5cb4`
- `0x1800f0990`
- `0x180172a70`
- `0x180172d00`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180172d59`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180172d59`
- `CoreMessaging!MsgBlobCreateShared` at `0x180172f4f`
- `CoreMessaging!MsgBlobCreateShared` at `0x180172f4f`
- `CoreMessaging!MsgRelease` at `0x18017300e`
- `CoreMessaging!MsgRelease` at `0x180173018`
- `CoreMessaging!MsgRelease` at `0x18017300e`
- `CoreMessaging!MsgRelease` at `0x180173018`
- `CoreMessaging!MsgStringCreateShared` at `0x180172f8e`
- `CoreMessaging!MsgStringCreateShared` at `0x180172f8e`
- `win32u!NtUserPostKeyboardInputMessage` at `0x180172e96`
- `win32u!NtUserPostKeyboardInputMessage` at `0x180172e96`

## string_xrefs

- `0x180173124`: `onecoreuap\windows\moderncore\inputv2\delivery\server\inputserviceproxy.cpp`
- `0x18017313d`: `onecoreuap\windows\moderncore\inputv2\delivery\server\inputserviceproxy.cpp`
- `0x180173156`: `onecoreuap\windows\moderncore\inputv2\delivery\server\inputserviceproxy.cpp`
- `0x18017316f`: `onecoreuap\windows\moderncore\inputv2\delivery\server\inputserviceproxy.cpp`
- `0x180173188`: `onecoreuap\windows\moderncore\inputv2\delivery\server\inputserviceproxy.cpp`

## pseudocode

```c
__int64 __fastcall InputServiceProxy::SendKeyboardEvent(
        InputServiceProxy *this,
        const struct KeyboardEvent *a2,
        unsigned int a3)
{
  unsigned int v4; // edi
  __int16 v5; // r15
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  bool v13; // zf
  __int16 v14; // ax
  __int16 v15; // cx
  unsigned __int16 v16; // r12
  _BYTE *v17; // rax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v22; // eax
  int v23; // eax
  int v24; // [rsp+20h] [rbp-99h]
  int v25; // [rsp+20h] [rbp-99h]
  bool v26[4]; // [rsp+70h] [rbp-49h] BYREF
  int v27; // [rsp+74h] [rbp-45h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+78h] [rbp-41h] BYREF
  int v29; // [rsp+80h] [rbp-39h] BYREF
  __int64 v30; // [rsp+88h] [rbp-31h] BYREF
  int v31; // [rsp+90h] [rbp-29h] BYREF
  int v32; // [rsp+94h] [rbp-25h] BYREF
  int v33; // [rsp+98h] [rbp-21h] BYREF
  int v34; // [rsp+9Ch] [rbp-1Dh] BYREF
  int v35; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v36; // [rsp+A8h] [rbp-11h] BYREF
  LARGE_INTEGER v37; // [rsp+B0h] [rbp-9h] BYREF
  __int128 v38; // [rsp+B8h] [rbp-1h] BYREF
  int v39; // [rsp+C8h] [rbp+Fh]
  unsigned __int16 v40[2]; // [rsp+D0h] [rbp+17h] BYREF
  __int16 v41; // [rsp+D4h] [rbp+1Bh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  *(_DWORD *)v40 = 0;
  v41 = 0;
  v4 = 0;
  v29 = 0;
  v5 = 0;
  v27 = 0;
  v36 = 0;
  v30 = 0;
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  if ( (unsigned int)dword_180241328 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180241328, 0x40000, v8, v9) )
  {
    v37 = PerformanceCount;
    v31 = *((unsigned __int16 *)a2 + 8);
    v32 = *((unsigned __int16 *)a2 + 9);
    *(_WORD *)v26 = *((_WORD *)a2 + 10);
    v33 = *((_DWORD *)a2 + 1);
    v34 = *(_DWORD *)a2;
    v35 = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v10,
      (unsigned int)&dword_180217314,
      v11,
      v12,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&v33,
      (__int64)v26,
      (__int64)&v32,
      (__int64)&v31,
      (__int64)&v37);
  }
  if ( !a3 || *((_DWORD *)a2 + 1) == 1 )
    goto LABEL_16;
  v13 = *(_DWORD *)a2 == 2;
  v38 = 0;
  v39 = 0;
  if ( v13 )
  {
    v14 = *((_WORD *)a2 + 10);
    v15 = 4327;
  }
  else
  {
    v15 = *((_WORD *)a2 + 9);
    v14 = *((unsigned __int8 *)a2 + 16);
  }
  v13 = (*((_BYTE *)a2 + 8) & 4) == 0;
  LOWORD(v38) = v14;
  WORD4(v38) = v15;
  if ( !v13 )
  {
    v15 |= 0x8000u;
    WORD4(v38) = v15;
  }
  if ( (*((_WORD *)a2 + 8) & 0xE100) == 0xE000 )
    WORD4(v38) = v15 | 0x100;
  HIDWORD(v38) = *((_DWORD *)a2 + 8);
  LOWORD(v39) = *((_WORD *)a2 + 11);
  if ( (int)NtUserPostKeyboardInputMessage(a3, &v38, &v27) >= 0 && v27 != *((_DWORD *)this + 13) )
  {
    *((_DWORD *)this + 13) = v27;
    v5 = 2048;
LABEL_16:
    if ( *(_DWORD *)a2 == 2 )
    {
      SurrogateCharAccumulator::OnKey(
        (InputServiceProxy *)((char *)this + 48),
        *((_WORD *)a2 + 10),
        (*((_BYTE *)a2 + 8) & 4) != 0,
        v26,
        v40,
        &v29);
      v4 = v29;
    }
    if ( *((_QWORD *)this + 4) )
    {
      v16 = 0;
      InputServiceProxy::SampleRandomPickStart(
        this,
        *(_DWORD *)a2,
        *((_DWORD *)a2 + 1),
        *((_WORD *)a2 + 10),
        *((_WORD *)a2 + 9),
        *((_WORD *)a2 + 8),
        PerformanceCount.QuadPart);
      v17 = (_BYTE *)*((_QWORD *)this + 7);
      if ( *v17 )
      {
        v16 = 4;
        *v17 = 0;
      }
      v18 = MsgBlobCreateShared((char *)a2 + 38, 256, &v30);
      if ( v18 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x10A,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\delivery\\server\\inputserviceproxy.cpp",
          (const char *)(unsigned int)v18,
          v24);
      if ( !*((_DWORD *)a2 + 1) )
      {
        if ( *(_DWORD *)a2 )
        {
          if ( *(_DWORD *)a2 == 1 )
          {
            LOWORD(v24) = *((_WORD *)a2 + 9);
            v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 32LL))(
                    *((_QWORD *)this + 4),
                    a3,
                    (unsigned __int16)(*((_WORD *)a2 + 4) | v5),
                    v16 | 8u);
            if ( v22 < 0 )
              wil::details::in1diag3::FailFast_Hr(
                retaddr,
                (void *)0x12C,
                (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\delivery\\server\\inputserviceproxy.cpp",
                (const char *)(unsigned int)v22,
                v24);
          }
          else if ( *(_DWORD *)a2 == 2 )
          {
            v19 = MsgStringCreateShared(v40, v4, &v36);
            if ( v19 < 0 )
              wil::details::in1diag3::FailFast_Hr(
                retaddr,
                (void *)0x135,
                (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\delivery\\server\\inputserviceproxy.cpp",
                (const char *)(unsigned int)v19,
                v24);
            LOWORD(v24) = *((_WORD *)a2 + 9);
            v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 40LL))(
                    *((_QWORD *)this + 4),
                    a3,
                    (unsigned __int16)(*((_WORD *)a2 + 4) | v5),
                    v16);
            if ( v20 < 0 )
              wil::details::in1diag3::FailFast_Hr(
                retaddr,
                (void *)0x141,
                (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\delivery\\server\\inputserviceproxy.cpp",
                (const char *)(unsigned int)v20,
                v24);
            MsgRelease(v36);
          }
        }
        else
        {
          v25 = *((_DWORD *)a2 + 3) | v16;
          v23 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 24LL))(
                  *((_QWORD *)this + 4),
                  a3,
                  *((unsigned __int16 *)a2 + 11),
                  (unsigned __int16)(*((_WORD *)a2 + 4) | v5));
          if ( v23 < 0 )
            wil::details::in1diag3::FailFast_Hr(
              retaddr,
              (void *)0x11D,
              (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\delivery\\server\\inputserviceproxy.cpp",
              (const char *)(unsigned int)v23,
              v25);
        }
      }
      MsgRelease(v30);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180172d00  mov     [rsp-8+arg_18], rbx
0x180172d05  push    rbp
0x180172d06  push    rsi
0x180172d07  push    rdi
0x180172d08  push    r12
0x180172d0a  push    r13
0x180172d0c  push    r14
0x180172d0e  push    r15
0x180172d10  lea     rbp, [rsp-27h]
0x180172d15  sub     rsp, 0E0h
0x180172d1c  mov     rax, cs:__security_cookie
0x180172d23  xor     rax, rsp
0x180172d26  mov     [rbp+57h+var_38], rax
0x180172d2a  xor     esi, esi
0x180172d2c  xor     eax, eax
0x180172d2e  mov     rbx, rcx
0x180172d31  mov     dword ptr [rbp+57h+var_40], eax
0x180172d34  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x180172d38  mov     [rbp+57h+var_3C], ax
0x180172d3c  mov     edi, esi
0x180172d3e  mov     [rbp+57h+var_90], esi
0x180172d41  mov     r15d, esi
0x180172d44  mov     [rbp+57h+var_9C], esi
0x180172d47  mov     [rbp+57h+var_68], rsi
0x180172d4b  mov     r13d, r8d
0x180172d4e  mov     [rbp+57h+var_88], rsi
0x180172d52  mov     r14, rdx
0x180172d55  mov     qword ptr [rbp+57h+PerformanceCount], rsi
0x180172d59  call    cs:__imp_QueryPerformanceCounter
0x180172d5f  mov     eax, cs:dword_180241328
0x180172d65  cmp     eax, 5
0x180172d68  jbe     loc_180172E07
0x180172d6e  mov     edx, 40000h
0x180172d73  lea     rcx, dword_180241328
0x180172d7a  call    _tlgKeywordOn
0x180172d7f  test    al, al
0x180172d81  jz      loc_180172E07
0x180172d87  mov     rax, qword ptr [rbp+57h+PerformanceCount]
0x180172d8b  lea     rdx, dword_180217314
0x180172d92  mov     [rbp+57h+var_60], rax
0x180172d96  movzx   eax, word ptr [r14+10h]
0x180172d9b  mov     [rbp+57h+var_80], eax
0x180172d9e  movzx   eax, word ptr [r14+12h]
0x180172da3  mov     [rbp+57h+var_7C], eax
0x180172da6  movzx   eax, word ptr [r14+14h]
0x180172dab  mov     word ptr [rbp+57h+var_A0], ax
0x180172daf  mov     eax, [r14+4]
0x180172db3  mov     [rbp+57h+var_78], eax
0x180172db6  mov     eax, [r14]
0x180172db9  mov     [rbp+57h+var_74], eax
0x180172dbc  lea     rax, [rbp+57h+var_60]
0x180172dc0  mov     [rsp+110h+var_C0], rax
0x180172dc5  lea     rax, [rbp+57h+var_80]
0x180172dc9  mov     [rsp+110h+var_C8], rax
0x180172dce  lea     rax, [rbp+57h+var_7C]
0x180172dd2  mov     [rsp+110h+var_D0], rax
0x180172dd7  lea     rax, [rbp+57h+var_A0]
0x180172ddb  mov     [rsp+110h+var_D8], rax
0x180172de0  lea     rax, [rbp+57h+var_78]
0x180172de4  mov     [rsp+110h+var_E0], rax
0x180172de9  lea     rax, [rbp+57h+var_74]
0x180172ded  mov     [rsp+110h+var_E8], rax
0x180172df2  lea     rax, [rbp+57h+var_70]
0x180172df6  mov     [rsp+110h+var_F0], rax
0x180172dfb  mov     [rbp+57h+var_70], 1
0x180172e02  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$01@@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$01@@33AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180172e07  test    r13d, r13d
0x180172e0a  jz      loc_180172EB9
0x180172e10  cmp     dword ptr [r14+4], 1
0x180172e15  jz      loc_180172EB9
0x180172e1b  xor     eax, eax
0x180172e1d  xorps   xmm0, xmm0
0x180172e20  cmp     dword ptr [r14], 2
0x180172e24  movups  [rbp+57h+var_58], xmm0
0x180172e28  mov     [rbp+57h+var_48], eax
0x180172e2b  jnz     short loc_180172E39
0x180172e2d  movzx   eax, word ptr [r14+14h]
0x180172e32  mov     ecx, 10E7h
0x180172e37  jmp     short loc_180172E43
0x180172e39  movzx   ecx, word ptr [r14+12h]
0x180172e3e  movzx   eax, byte ptr [r14+10h]
0x180172e43  test    byte ptr [r14+8], 4
0x180172e48  mov     word ptr [rbp+57h+var_58], ax
0x180172e4c  mov     word ptr [rbp+57h+var_58+8], cx
0x180172e50  jz      short loc_180172E5B
0x180172e52  or      cx, 8000h
0x180172e57  mov     word ptr [rbp+57h+var_58+8], cx
0x180172e5b  movzx   eax, word ptr [r14+10h]
0x180172e60  mov     edx, 0E100h
0x180172e65  and     ax, dx
0x180172e68  mov     edx, 0E000h
0x180172e6d  cmp     ax, dx
0x180172e70  jnz     short loc_180172E7B
0x180172e72  or      cx, 100h
0x180172e77  mov     word ptr [rbp+57h+var_58+8], cx
0x180172e7b  mov     eax, [r14+20h]
0x180172e7f  lea     r8, [rbp+57h+var_9C]
0x180172e83  mov     dword ptr [rbp+57h+var_58+0Ch], eax
0x180172e86  lea     rdx, [rbp+57h+var_58]
0x180172e8a  movzx   eax, word ptr [r14+16h]
0x180172e8f  mov     ecx, r13d
0x180172e92  mov     word ptr [rbp+57h+var_48], ax
0x180172e96  call    cs:__imp_NtUserPostKeyboardInputMessage
0x180172e9c  test    eax, eax
0x180172e9e  js      loc_18017301E
0x180172ea4  mov     eax, [rbp+57h+var_9C]
0x180172ea7  cmp     eax, [rbx+34h]
0x180172eaa  jz      loc_18017301E
0x180172eb0  mov     [rbx+34h], eax
0x180172eb3  mov     r15d, 800h
0x180172eb9  cmp     dword ptr [r14], 2
0x180172ebd  jnz     short loc_180172EF2
0x180172ebf  mov     r8b, [r14+8]
0x180172ec3  lea     rax, [rbp+57h+var_90]
0x180172ec7  movzx   edx, word ptr [r14+14h]; unsigned __int16
0x180172ecc  lea     rcx, [rbx+30h]; this
0x180172ed0  mov     [rsp+110h+var_E8], rax; int *
0x180172ed5  lea     r9, [rbp+57h+var_A0]; bool *
0x180172ed9  shr     r8b, 2
0x180172edd  lea     rax, [rbp+57h+var_40]
0x180172ee1  and     r8b, 1; bool
0x180172ee5  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x180172eea  call    ?OnKey@SurrogateCharAccumulator@@QEAAXG_NAEA_NQEAGAEAH@Z; SurrogateCharAccumulator::OnKey(ushort,bool,bool &,ushort * const,int &)
0x180172eef  mov     edi, [rbp+57h+var_90]
0x180172ef2  cmp     [rbx+20h], rsi
0x180172ef6  jz      loc_18017301E
0x180172efc  mov     rax, qword ptr [rbp+57h+PerformanceCount]
0x180172f00  mov     rcx, rbx; this
0x180172f03  movzx   r9d, word ptr [r14+14h]; unsigned __int16
0x180172f08  mov     r12d, esi
0x180172f0b  mov     r8d, [r14+4]; unsigned int
0x180172f0f  mov     edx, [r14]; unsigned int
0x180172f12  mov     [rsp+110h+var_E0], rax; unsigned __int64
0x180172f17  movzx   eax, word ptr [r14+10h]
0x180172f1c  mov     word ptr [rsp+110h+var_E8], ax; unsigned __int16
0x180172f21  movzx   eax, word ptr [r14+12h]
0x180172f26  mov     word ptr [rsp+110h+var_F0], ax; int
0x180172f2b  call    ?SampleRandomPickStart@InputServiceProxy@@AEAAXIIGGG_K@Z; InputServiceProxy::SampleRandomPickStart(uint,uint,ushort,ushort,ushort,unsigned __int64)
0x180172f30  mov     rax, [rbx+38h]
0x180172f34  cmp     [rax], sil
0x180172f37  jz      short loc_180172F42
0x180172f39  mov     r12d, 4
0x180172f3f  mov     [rax], sil
0x180172f42  lea     rcx, [r14+26h]
0x180172f46  mov     edx, 100h
0x180172f4b  lea     r8, [rbp+57h+var_88]
0x180172f4f  call    cs:__imp_MsgBlobCreateShared
0x180172f55  test    eax, eax
0x180172f57  js      loc_18017316B
0x180172f5d  cmp     [r14+4], esi
0x180172f61  jnz     loc_180173014
0x180172f67  mov     ecx, [r14]
0x180172f6a  test    ecx, ecx
0x180172f6c  jz      loc_1801730A6
0x180172f72  sub     ecx, 1
0x180172f75  jz      loc_180173047
0x180172f7b  cmp     ecx, 1
0x180172f7e  jnz     loc_180173014
0x180172f84  lea     r8, [rbp+57h+var_68]
0x180172f88  mov     edx, edi
0x180172f8a  lea     rcx, [rbp+57h+var_40]
0x180172f8e  call    cs:__imp_MsgStringCreateShared
0x180172f94  test    eax, eax
0x180172f96  js      loc_180173184
0x180172f9c  mov     rcx, [rbx+20h]
0x180172fa0  xor     edi, edi
0x180172fa2  mov     r8, qword ptr [rbp+57h+PerformanceCount]
0x180172fa6  xor     ebx, ebx
0x180172fa8  mov     r10d, [rbp+57h+var_9C]
0x180172fac  mov     edx, r13d
0x180172faf  mov     r11, [rbp+57h+var_88]
0x180172fb3  mov     rax, [rcx]
0x180172fb6  mov     rsi, [rbp+57h+var_68]
0x180172fba  or      r15w, [r14+8]
0x180172fbf  mov     [rsp+110h+var_B8], r8
0x180172fc4  mov     r8d, [r14+20h]
0x180172fc8  mov     rax, [rax+28h]
0x180172fcc  mov     dword ptr [rsp+110h+var_C0], r10d
0x180172fd1  mov     [rsp+110h+var_C8], r11
0x180172fd6  mov     dword ptr [rsp+110h+var_D0], r8d
0x180172fdb  movzx   r8d, word ptr [r14+12h]
0x180172fe0  mov     word ptr [rsp+110h+var_D8], bx
0x180172fe5  mov     word ptr [rsp+110h+var_E0], di
0x180172fea  mov     [rsp+110h+var_E8], rsi
0x180172fef  mov     word ptr [rsp+110h+var_F0], r8w; int
0x180172ff5  movzx   r8d, r15w
0x180172ff9  movzx   r9d, r12w
0x180172ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180173002  test    eax, eax
0x180173004  js      loc_180173120
0x18017300a  mov     rcx, [rbp+57h+var_68]
0x18017300e  call    cs:__imp_MsgRelease
0x180173014  mov     rcx, [rbp+57h+var_88]
0x180173018  call    cs:__imp_MsgRelease
0x18017301e  xor     eax, eax
0x180173020  mov     rcx, [rbp+57h+var_38]
0x180173024  xor     rcx, rsp; StackCookie
0x180173027  call    __security_check_cookie
0x18017302c  mov     rbx, [rsp+110h+arg_18]
0x180173034  add     rsp, 0E0h
0x18017303b  pop     r15
0x18017303d  pop     r14
0x18017303f  pop     r13
0x180173041  pop     r12
0x180173043  pop     rdi
0x180173044  pop     rsi
0x180173045  pop     rbp
0x180173046  retn
0x180173047  mov     rdx, qword ptr [rbp+57h+PerformanceCount]
0x18017304b  mov     r8d, [rbp+57h+var_9C]
0x18017304f  mov     rcx, [rbx+20h]
0x180173053  mov     r10, [rbp+57h+var_88]
0x180173057  or      r15w, [r14+8]
0x18017305c  mov     [rsp+110h+var_D0], rdx
0x180173061  mov     rdx, [r14+18h]
0x180173065  mov     rax, [rcx]
0x180173068  mov     dword ptr [rsp+110h+var_D8], r8d
0x18017306d  movzx   r8d, r15w
0x180173071  mov     [rsp+110h+var_E0], rdx
0x180173076  movzx   edx, word ptr [r14+12h]
0x18017307b  mov     rax, [rax+20h]
0x18017307f  movzx   r9d, r12w
0x180173083  mov     [rsp+110h+var_E8], r10
0x180173088  or      r9d, 8
0x18017308c  mov     word ptr [rsp+110h+var_F0], dx; int
0x180173091  mov     edx, r13d
0x180173094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180173099  test    eax, eax
0x18017309b  js      loc_180173139
0x1801730a1  jmp     loc_180173014
0x1801730a6  mov     rcx, [rbx+20h]
0x1801730aa  mov     rdx, qword ptr [rbp+57h+PerformanceCount]
0x1801730ae  mov     r9d, [rbp+57h+var_9C]
0x1801730b2  mov     r10, [rbp+57h+var_88]
0x1801730b6  mov     rax, [rcx]
0x1801730b9  or      r15w, [r14+8]
0x1801730be  movzx   r8d, word ptr [r14+16h]
0x1801730c3  movzx   r11d, r12w
0x1801730c7  mov     rbx, [rax+18h]
0x1801730cb  movzx   eax, word ptr [r14+24h]
0x1801730d0  or      r11d, [r14+0Ch]
0x1801730d4  mov     word ptr [rsp+110h+var_B8], ax
0x1801730d9  mov     rax, rbx
0x1801730dc  mov     [rsp+110h+var_C0], rdx
0x1801730e1  mov     rdx, [r14+18h]
0x1801730e5  mov     dword ptr [rsp+110h+var_C8], r9d
0x1801730ea  movzx   r9d, r15w
0x1801730ee  mov     [rsp+110h+var_D0], rdx
0x1801730f3  mov     edx, [r14+20h]
0x1801730f7  mov     [rsp+110h+var_D8], r10
0x1801730fc  mov     dword ptr [rsp+110h+var_E0], edx
0x180173100  movzx   edx, word ptr [r14+10h]
0x180173105  mov     word ptr [rsp+110h+var_E8], dx
0x18017310a  mov     edx, r13d
0x18017310d  mov     dword ptr [rsp+110h+var_F0], r11d; int
0x180173112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180173117  test    eax, eax
0x180173119  js      short loc_180173152
0x18017311b  jmp     loc_180173014
0x180173120  mov     rcx, [rbp+5Fh]; this
0x180173124  lea     r8, aOnecoreuapWind_163; "onecoreuap\\windows\\moderncore\\inputv"...
0x18017312b  mov     r9d, eax; char *
0x18017312e  mov     edx, 141h; void *
0x180173133  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180173139  mov     rcx, [rbp+5Fh]; this
0x18017313d  lea     r8, aOnecoreuapWind_163; "onecoreuap\\windows\\moderncore\\inputv"...
0x180173144  mov     r9d, eax; char *
0x180173147  mov     edx, 12Ch; void *
0x18017314c  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180173152  mov     rcx, [rbp+5Fh]; this
0x180173156  lea     r8, aOnecoreuapWind_163; "onecoreuap\\windows\\moderncore\\inputv"...
0x18017315d  mov     r9d, eax; char *
0x180173160  mov     edx, 11Dh; void *
0x180173165  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18017316b  mov     rcx, [rbp+5Fh]; this
0x18017316f  lea     r8, aOnecoreuapWind_163; "onecoreuap\\windows\\moderncore\\inputv"...
0x180173176  mov     r9d, eax; char *
0x180173179  mov     edx, 10Ah; void *
0x18017317e  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180173184  mov     rcx, [rbp+5Fh]; this
0x180173188  lea     r8, aOnecoreuapWind_163; "onecoreuap\\windows\\moderncore\\inputv"...
0x18017318f  mov     r9d, eax; char *
0x180173192  mov     edx, 135h; void *
0x180173197  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
```
