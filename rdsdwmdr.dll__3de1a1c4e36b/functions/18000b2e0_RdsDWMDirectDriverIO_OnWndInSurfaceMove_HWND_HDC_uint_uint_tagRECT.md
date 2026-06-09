# RdsDWMDirectDriverIO::OnWndInSurfaceMove(HWND__ *,HDC__ *,uint,uint,tagRECT *)

- ea: `0x18000b2e0`
- end: `0x18000b4c8`
- name: `?OnWndInSurfaceMove@RdsDWMDirectDriverIO@@UEAAJPEAUHWND__@@PEAUHDC__@@IIPEAUtagRECT@@@Z`
- size: `488`
- prototype: `__int64 __fastcall(RdsDWMDirectDriverIO *this, const unsigned __int16 *, __int64, __int64, unsigned int, struct tagRECT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180001188`
- `0x18000251c`
- `0x18000b2e0`
- `0x18000bdbc`
- `0x18002b93a`
- `0x18002b960`

## string_xrefs

- `0x18000b466`: `SendToRemoteDriver:Failed to send surface update event`
- `0x18000b348`: `Sending in-surface move notification for windowId=0x%p hdc=0x%I64x src=(%d, %d) dst=(%d, %d, %d, %d).`
- `0x18000b450`: `OnWndInSurfaceMove`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectDriverIO::OnWndInSurfaceMove(
        RdsDWMDirectDriverIO *this,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        struct tagRECT *a6)
{
  int v6; // r12d
  __int128 v8; // xmm0
  int v9; // eax
  int v10; // r9d
  int v11; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned int v14; // ebx
  unsigned __int8 *v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+70h] [rbp-90h] BYREF
  LONG bottom; // [rsp+74h] [rbp-8Ch] BYREF
  LONG right; // [rsp+78h] [rbp-88h] BYREF
  LONG top; // [rsp+7Ch] [rbp-84h] BYREF
  LONG left; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v22; // [rsp+84h] [rbp-7Ch] BYREF
  const char *v23; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 v24[8]; // [rsp+90h] [rbp-70h] BYREF
  const char *v25; // [rsp+98h] [rbp-68h] BYREF
  __int64 v26; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 v27[4]; // [rsp+B0h] [rbp-50h] BYREF
  int v28; // [rsp+B4h] [rbp-4Ch]
  __int64 v29; // [rsp+B8h] [rbp-48h]
  int v30; // [rsp+C0h] [rbp-40h]
  int v31; // [rsp+CCh] [rbp-34h]
  __int64 v32; // [rsp+D0h] [rbp-30h]
  __int64 v33; // [rsp+D8h] [rbp-28h]
  __int128 v34; // [rsp+E0h] [rbp-20h]
  __int64 v35; // [rsp+F0h] [rbp-10h]
  int v36; // [rsp+100h] [rbp+0h]
  unsigned int v37; // [rsp+104h] [rbp+4h]
  int v38; // [rsp+108h] [rbp+8h]
  int v39; // [rsp+10Ch] [rbp+Ch]
  int v40; // [rsp+120h] [rbp+20h]

  v6 = a4;
  v25 = (const char *)this;
  if ( (unsigned int)dword_180044008 > 5 )
  {
    bottom = a6->bottom;
    right = a6->right;
    top = a6->top;
    left = a6->left;
    *(_QWORD *)v24 = "Sending in-surface move notification for windowId=0x%p hdc=0x%I64x src=(%d, %d) dst=(%d, %d, %d, %d).";
    v23 = (const char *)a2;
    v22 = a5;
    v17 = a4;
    v26 = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)&dword_180037E74,
      a3,
      a4,
      (const unsigned __int16 **)v24,
      (__int64)&v23,
      (__int64)&v26,
      (__int64)&v17,
      (__int64)&v22,
      (__int64)&left,
      (__int64)&top,
      (__int64)&right,
      (__int64)&bottom);
  }
  memset_0(v27, 0, 0x84u);
  v8 = (__int128)*a6;
  *(_DWORD *)v27 = 132;
  v35 = 0;
  v29 = 2;
  v31 = 2;
  v38 = a6->bottom - a6->top;
  v9 = a6->right - a6->left;
  v40 = 0;
  v39 = v9;
  v28 = -1884332398;
  v30 = 120;
  v32 = a3;
  v33 = a3;
  v36 = v6;
  v37 = a5;
  v34 = v8;
  v11 = RdsDWMDirectDriverIO::SendToRemoteDriver((RdsDWMDirectDriverIO *)(v25 - 48), 132, v27, v10, v16);
  v14 = v11;
  if ( v11 < 0 && (unsigned int)dword_180044008 > 3 )
  {
    v17 = v11;
    v25 = "OnWndInSurfaceMove";
    *(_QWORD *)v24 = "SendToRemoteDriver:Failed to send surface update event";
    v23 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)dword_180044008,
      (__int64)byte_180037E31,
      v12,
      v13,
      (const unsigned __int16 **)&v23,
      (const unsigned __int16 **)v24,
      (__int64)&v17,
      (const unsigned __int16 **)&v25);
  }
  return v14;
}

```

## disassembly

```asm
0x18000b2e0  push    rbp
0x18000b2e2  push    rbx
0x18000b2e3  push    rsi
0x18000b2e4  push    rdi
0x18000b2e5  push    r12
0x18000b2e7  push    r13
0x18000b2e9  push    r14
0x18000b2eb  push    r15
0x18000b2ed  lea     rbp, [rsp-58h]
0x18000b2f2  sub     rsp, 158h
0x18000b2f9  mov     rax, cs:__security_cookie
0x18000b300  xor     rax, rsp
0x18000b303  mov     [rbp+90h+var_50], rax
0x18000b307  mov     eax, cs:dword_180044008
0x18000b30d  mov     r12d, r9d
0x18000b310  mov     rbx, [rbp+90h+arg_28]
0x18000b317  mov     r15, r8
0x18000b31a  mov     r13d, [rbp+90h+arg_20]
0x18000b321  mov     [rbp+90h+var_F8], rcx
0x18000b325  cmp     eax, 5
0x18000b328  jbe     loc_18000B3C5
0x18000b32e  mov     eax, [rbx+0Ch]
0x18000b331  mov     [rsp+190h+var_11C], eax
0x18000b335  mov     eax, [rbx+8]
0x18000b338  mov     [rsp+190h+var_118], eax
0x18000b33c  mov     eax, [rbx+4]
0x18000b33f  mov     [rsp+190h+var_114], eax
0x18000b343  mov     eax, [rbx]
0x18000b345  mov     [rbp+90h+var_110], eax
0x18000b348  lea     rax, aSendingInSurfa; "Sending in-surface move notification fo"...
0x18000b34f  mov     qword ptr [rbp+90h+var_100], rax
0x18000b353  lea     rax, [rsp+190h+var_11C]
0x18000b358  mov     [rsp+190h+var_130], rax
0x18000b35d  lea     rax, [rsp+190h+var_118]
0x18000b362  mov     [rsp+190h+var_138], rax
0x18000b367  lea     rax, [rsp+190h+var_114]
0x18000b36c  mov     [rsp+190h+var_140], rax
0x18000b371  lea     rax, [rbp+90h+var_110]
0x18000b375  mov     [rsp+190h+var_148], rax
0x18000b37a  lea     rax, [rbp+90h+var_10C]
0x18000b37e  mov     [rsp+190h+var_150], rax
0x18000b383  lea     rax, [rsp+190h+var_120]
0x18000b388  mov     [rsp+190h+var_158], rax
0x18000b38d  lea     rax, [rbp+90h+var_F0]
0x18000b391  mov     [rsp+190h+var_160], rax
0x18000b396  lea     rax, [rbp+90h+var_108]
0x18000b39a  mov     [rsp+190h+var_168], rax
0x18000b39f  lea     rax, [rbp+90h+var_100]
0x18000b3a3  mov     [rbp+90h+var_108], rdx
0x18000b3a7  lea     rdx, dword_180037E74
0x18000b3ae  mov     [rsp+190h+var_170], rax; unsigned __int8 *
0x18000b3b3  mov     [rbp+90h+var_10C], r13d
0x18000b3b7  mov     [rsp+190h+var_120], r9d
0x18000b3bc  mov     [rbp+90h+var_F0], r8
0x18000b3c0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4AEBU?$_tlgWrapperByVal@$03@@55555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000b3c5  xor     edx, edx; Val
0x18000b3c7  lea     rcx, [rbp+90h+var_E0]; void *
0x18000b3cb  mov     r8d, 84h; Size
0x18000b3d1  call    memset_0
0x18000b3d6  movups  xmm0, xmmword ptr [rbx]
0x18000b3d9  xor     ecx, ecx
0x18000b3db  mov     dword ptr [rbp+90h+var_E0], 84h
0x18000b3e2  mov     eax, 2
0x18000b3e7  mov     [rbp+90h+var_A0], rcx
0x18000b3eb  mov     [rbp+90h+var_D8], rax
0x18000b3ef  lea     r8, [rbp+90h+var_E0]; unsigned __int8 *
0x18000b3f3  mov     [rbp+90h+var_C4], eax
0x18000b3f6  mov     edx, 84h; int
0x18000b3fb  mov     eax, [rbx+0Ch]
0x18000b3fe  sub     eax, [rbx+4]
0x18000b401  mov     [rbp+90h+var_88], eax
0x18000b404  mov     eax, [rbx+8]
0x18000b407  sub     eax, [rbx]
0x18000b409  mov     [rbp+90h+var_70], ecx
0x18000b40c  mov     rcx, [rbp+90h+var_F8]
0x18000b410  add     rcx, 0FFFFFFFFFFFFFFD0h; this
0x18000b414  mov     [rbp+90h+var_84], eax
0x18000b417  mov     [rbp+90h+var_DC], 8FAF5E92h
0x18000b41e  mov     [rbp+90h+var_D0], 78h ; 'x'
0x18000b425  mov     [rbp+90h+var_C0], r15
0x18000b429  mov     [rbp+90h+var_B8], r15
0x18000b42d  mov     [rbp+90h+var_90], r12d
0x18000b431  mov     [rbp+90h+var_8C], r13d
0x18000b435  movdqu  [rbp+90h+var_B0], xmm0
0x18000b43a  call    ?SendToRemoteDriver@RdsDWMDirectDriverIO@@IEAAJHPEAEH0@Z; RdsDWMDirectDriverIO::SendToRemoteDriver(int,uchar *,int,uchar *)
0x18000b43f  mov     ebx, eax
0x18000b441  test    eax, eax
0x18000b443  jns     short loc_18000B4A6
0x18000b445  mov     ecx, cs:dword_180044008
0x18000b44b  cmp     ecx, 3
0x18000b44e  jbe     short loc_18000B4A6
0x18000b450  lea     rax, aOnwndinsurface; "OnWndInSurfaceMove"
0x18000b457  mov     [rsp+190h+var_120], ebx
0x18000b45b  mov     [rbp+90h+var_F8], rax
0x18000b45f  lea     rdx, byte_180037E31
0x18000b466  lea     rax, aSendtoremotedr; "SendToRemoteDriver:Failed to send surfa"...
0x18000b46d  mov     qword ptr [rbp+90h+var_100], rax
0x18000b471  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18000b478  mov     [rbp+90h+var_108], rax
0x18000b47c  lea     rax, [rbp+90h+var_F8]
0x18000b480  mov     [rsp+190h+var_158], rax
0x18000b485  lea     rax, [rsp+190h+var_120]
0x18000b48a  mov     [rsp+190h+var_160], rax
0x18000b48f  lea     rax, [rbp+90h+var_100]
0x18000b493  mov     [rsp+190h+var_168], rax
0x18000b498  lea     rax, [rbp+90h+var_108]
0x18000b49c  mov     [rsp+190h+var_170], rax
0x18000b4a1  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000b4a6  mov     eax, ebx
0x18000b4a8  mov     rcx, [rbp+90h+var_50]
0x18000b4ac  xor     rcx, rsp; StackCookie
0x18000b4af  call    __security_check_cookie
0x18000b4b4  add     rsp, 158h
0x18000b4bb  pop     r15
0x18000b4bd  pop     r14
0x18000b4bf  pop     r13
0x18000b4c1  pop     r12
0x18000b4c3  pop     rdi
0x18000b4c4  pop     rsi
0x18000b4c5  pop     rbx
0x18000b4c6  pop     rbp
0x18000b4c7  retn
```
