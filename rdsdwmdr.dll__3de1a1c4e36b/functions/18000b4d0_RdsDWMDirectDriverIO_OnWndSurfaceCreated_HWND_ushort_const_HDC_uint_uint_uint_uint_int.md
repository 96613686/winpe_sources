# RdsDWMDirectDriverIO::OnWndSurfaceCreated(HWND__ *,ushort const *,HDC__ *,uint,uint,uint,uint,int)

- ea: `0x18000b4d0`
- end: `0x18000b6d0`
- name: `?OnWndSurfaceCreated@RdsDWMDirectDriverIO@@UEAAJPEAUHWND__@@PEBGPEAUHDC__@@IIIIH@Z`
- size: `512`
- prototype: `__int64 __fastcall(RdsDWMDirectDriverIO *__hidden this, HWND, const unsigned __int16 *, HDC, unsigned int, unsigned int, unsigned int, unsigned int, int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001188`
- `0x180002444`
- `0x18000b4d0`
- `0x18000bdbc`
- `0x18002b93a`
- `0x18002b960`

## string_xrefs

- `0x18000b524`: `Sending surface created notification`
- `0x18000b64a`: `OnWndSurfaceCreated`
- `0x18000b661`: `SendToRemoteDriver:Failed to send surface create evemt`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectDriverIO::OnWndSurfaceCreated(
        RdsDWMDirectDriverIO *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        int a9)
{
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  int v20; // r9d
  int v21; // eax
  __int64 v22; // r8
  __int64 v23; // r9
  unsigned int v24; // ebx
  unsigned __int8 *v26; // [rsp+20h] [rbp-E0h]
  unsigned int v27; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v29; // [rsp+58h] [rbp-A8h] BYREF
  const char *v30; // [rsp+60h] [rbp-A0h] BYREF
  const char *v31; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 v32[8]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v33[4]; // [rsp+80h] [rbp-80h] BYREF
  int v34; // [rsp+84h] [rbp-7Ch]
  int v35; // [rsp+88h] [rbp-78h]
  int v36; // [rsp+8Ch] [rbp-74h]
  int v37; // [rsp+90h] [rbp-70h]
  _BYTE v38[8]; // [rsp+94h] [rbp-6Ch] BYREF
  __int128 v39; // [rsp+9Ch] [rbp-64h]
  __int128 v40; // [rsp+ACh] [rbp-54h]
  __int128 v41; // [rsp+BCh] [rbp-44h]
  __int128 v42; // [rsp+CCh] [rbp-34h]
  __int128 v43; // [rsp+DCh] [rbp-24h]
  __int128 v44; // [rsp+ECh] [rbp-14h]
  __int128 v45; // [rsp+FCh] [rbp-4h]
  __int128 v46; // [rsp+10Ch] [rbp+Ch]
  unsigned int v47; // [rsp+11Ch] [rbp+1Ch]
  unsigned int v48; // [rsp+120h] [rbp+20h]
  unsigned int v49; // [rsp+124h] [rbp+24h]
  unsigned int v50; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v51; // [rsp+12Ch] [rbp+2Ch]
  int v52; // [rsp+134h] [rbp+34h]
  int v53; // [rsp+138h] [rbp+38h]

  if ( (unsigned int)dword_180044008 > 4 )
  {
    v31 = (const char *)a2;
    *(_QWORD *)v32 = "Sending surface created notification";
    v28 = a9;
    v29 = a8;
    v27 = a7;
    v30 = (const char *)a4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)&byte_1800380E7,
      (__int64)a3,
      (__int64)a4,
      (const unsigned __int16 **)v32,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v27,
      (__int64)&v29,
      (__int64)&v28);
  }
  memset_0(v38, 0, 0x88u);
  v12 = *(_OWORD *)a3;
  v13 = *((_OWORD *)a3 + 1);
  v47 = a6;
  v39 = v12;
  *(_DWORD *)v33 = 188;
  v14 = *((_OWORD *)a3 + 2);
  v34 = -1884332398;
  v40 = v13;
  v35 = 2;
  v15 = *((_OWORD *)a3 + 3);
  v36 = 10;
  v41 = v14;
  v37 = 176;
  v16 = *((_OWORD *)a3 + 4);
  v48 = a8;
  v42 = v15;
  v49 = a7;
  v17 = *((_OWORD *)a3 + 5);
  v50 = a5;
  v43 = v16;
  v51 = a4;
  v18 = *((_OWORD *)a3 + 6);
  v53 = a9;
  v44 = v17;
  v52 = 1;
  v19 = *((_OWORD *)a3 + 7);
  v45 = v18;
  v46 = v19;
  v21 = RdsDWMDirectDriverIO::SendToRemoteDriver((RdsDWMDirectDriverIO *)((char *)this - 48), 188, v33, v20, v26);
  v24 = v21;
  if ( v21 < 0 && (unsigned int)dword_180044008 > 3 )
  {
    v27 = v21;
    *(_QWORD *)v32 = "OnWndSurfaceCreated";
    v31 = "SendToRemoteDriver:Failed to send surface create evemt";
    v30 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)dword_180044008,
      (__int64)&dword_1800380A4,
      v22,
      v23,
      (const unsigned __int16 **)&v30,
      (const unsigned __int16 **)&v31,
      (__int64)&v27,
      (const unsigned __int16 **)v32);
  }
  return v24;
}

```

## disassembly

```asm
0x18000b4d0  mov     [rsp-8+arg_8], rbx
0x18000b4d5  mov     [rsp-8+arg_10], rsi
0x18000b4da  push    rbp
0x18000b4db  push    rdi
0x18000b4dc  push    r13
0x18000b4de  push    r14
0x18000b4e0  push    r15
0x18000b4e2  lea     rbp, [rsp-50h]
0x18000b4e7  sub     rsp, 150h
0x18000b4ee  mov     rax, cs:__security_cookie
0x18000b4f5  xor     rax, rsp
0x18000b4f8  mov     [rbp+70h+var_30], rax
0x18000b4fc  mov     eax, cs:dword_180044008
0x18000b502  mov     rdi, r9
0x18000b505  mov     esi, [rbp+70h+arg_40]
0x18000b50b  mov     rbx, r8
0x18000b50e  mov     r14d, [rbp+70h+arg_38]
0x18000b515  mov     r13, rcx
0x18000b518  mov     r15d, [rbp+70h+arg_30]
0x18000b51f  cmp     eax, 4
0x18000b522  jbe     short loc_18000B590
0x18000b524  lea     rax, aSendingSurface_1; "Sending surface created notification"
0x18000b52b  mov     [rsp+170h+var_108], rdx
0x18000b530  mov     qword ptr [rsp+170h+var_100], rax
0x18000b535  lea     rdx, byte_1800380E7
0x18000b53c  lea     rax, [rsp+170h+var_11C]
0x18000b541  mov     [rsp+170h+var_11C], esi
0x18000b545  mov     [rsp+170h+var_128], rax
0x18000b54a  lea     rax, [rsp+170h+var_118]
0x18000b54f  mov     [rsp+170h+var_130], rax
0x18000b554  lea     rax, [rsp+170h+var_120]
0x18000b559  mov     [rsp+170h+var_138], rax
0x18000b55e  lea     rax, [rsp+170h+var_110]
0x18000b563  mov     [rsp+170h+var_140], rax
0x18000b568  lea     rax, [rsp+170h+var_108]
0x18000b56d  mov     [rsp+170h+var_148], rax
0x18000b572  lea     rax, [rsp+170h+var_100]
0x18000b577  mov     [rsp+170h+var_150], rax; unsigned __int8 *
0x18000b57c  mov     [rsp+170h+var_118], r14d
0x18000b581  mov     [rsp+170h+var_120], r15d
0x18000b586  mov     [rsp+170h+var_110], r9
0x18000b58b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@U?$_tlgWrapperByVal@$03@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4AEBU?$_tlgWrapperByVal@$03@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000b590  xor     edx, edx; Val
0x18000b592  lea     rcx, [rbp+70h+var_DC]; void *
0x18000b596  mov     r8d, 88h; Size
0x18000b59c  call    memset_0
0x18000b5a1  movups  xmm0, xmmword ptr [rbx]
0x18000b5a4  mov     eax, [rbp+70h+arg_28]
0x18000b5aa  mov     edx, 0BCh; int
0x18000b5af  movups  xmm1, xmmword ptr [rbx+10h]
0x18000b5b3  mov     [rbp+70h+var_54], eax
0x18000b5b6  lea     rcx, [r13-30h]; this
0x18000b5ba  mov     eax, [rbp+70h+arg_20]
0x18000b5c0  lea     r8, [rbp+70h+var_F0]; unsigned __int8 *
0x18000b5c4  movups  [rbp+70h+var_D4], xmm0
0x18000b5c8  mov     dword ptr [rbp+70h+var_F0], edx
0x18000b5cb  movups  xmm0, xmmword ptr [rbx+20h]
0x18000b5cf  mov     [rbp+70h+var_EC], 8FAF5E92h
0x18000b5d6  movups  [rbp+70h+var_C4], xmm1
0x18000b5da  mov     [rbp+70h+var_E8], 2
0x18000b5e1  movups  xmm1, xmmword ptr [rbx+30h]
0x18000b5e5  mov     [rbp+70h+var_E4], 0Ah
0x18000b5ec  movups  [rbp+70h+var_B4], xmm0
0x18000b5f0  mov     [rbp+70h+var_E0], 0B0h
0x18000b5f7  movups  xmm0, xmmword ptr [rbx+40h]
0x18000b5fb  mov     [rbp+70h+var_50], r14d
0x18000b5ff  movups  [rbp+70h+var_A4], xmm1
0x18000b603  mov     [rbp+70h+var_4C], r15d
0x18000b607  movups  xmm1, xmmword ptr [rbx+50h]
0x18000b60b  mov     [rbp+70h+var_48], eax
0x18000b60e  movups  [rbp+70h+var_94], xmm0
0x18000b612  mov     [rbp+70h+var_44], rdi
0x18000b616  movups  xmm0, xmmword ptr [rbx+60h]
0x18000b61a  mov     [rbp+70h+var_38], esi
0x18000b61d  movups  [rbp+70h+var_84], xmm1
0x18000b621  mov     [rbp+70h+var_3C], 1
0x18000b628  movups  xmm1, xmmword ptr [rbx+70h]
0x18000b62c  movups  [rbp+70h+var_74], xmm0
0x18000b630  movups  [rbp+70h+var_64], xmm1
0x18000b634  call    ?SendToRemoteDriver@RdsDWMDirectDriverIO@@IEAAJHPEAEH0@Z; RdsDWMDirectDriverIO::SendToRemoteDriver(int,uchar *,int,uchar *)
0x18000b639  mov     ebx, eax
0x18000b63b  test    eax, eax
0x18000b63d  jns     short loc_18000B6A6
0x18000b63f  mov     ecx, cs:dword_180044008
0x18000b645  cmp     ecx, 3
0x18000b648  jbe     short loc_18000B6A6
0x18000b64a  lea     rax, aOnwndsurfacecr; "OnWndSurfaceCreated"
0x18000b651  mov     [rsp+170h+var_120], ebx
0x18000b655  mov     qword ptr [rsp+170h+var_100], rax
0x18000b65a  lea     rdx, dword_1800380A4
0x18000b661  lea     rax, aSendtoremotedr_5; "SendToRemoteDriver:Failed to send surfa"...
0x18000b668  mov     [rsp+170h+var_108], rax
0x18000b66d  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18000b674  mov     [rsp+170h+var_110], rax
0x18000b679  lea     rax, [rsp+170h+var_100]
0x18000b67e  mov     [rsp+170h+var_138], rax
0x18000b683  lea     rax, [rsp+170h+var_120]
0x18000b688  mov     [rsp+170h+var_140], rax
0x18000b68d  lea     rax, [rsp+170h+var_108]
0x18000b692  mov     [rsp+170h+var_148], rax
0x18000b697  lea     rax, [rsp+170h+var_110]
0x18000b69c  mov     [rsp+170h+var_150], rax
0x18000b6a1  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000b6a6  mov     eax, ebx
0x18000b6a8  mov     rcx, [rbp+70h+var_30]
0x18000b6ac  xor     rcx, rsp; StackCookie
0x18000b6af  call    __security_check_cookie
0x18000b6b4  lea     r11, [rsp+170h+var_20]
0x18000b6bc  mov     rbx, [r11+38h]
0x18000b6c0  mov     rsi, [r11+40h]
0x18000b6c4  mov     rsp, r11
0x18000b6c7  pop     r15
0x18000b6c9  pop     r14
0x18000b6cb  pop     r13
0x18000b6cd  pop     rdi
0x18000b6ce  pop     rbp
0x18000b6cf  retn
```
