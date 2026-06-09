# CMsftDiscFormat2TrackAtOnce::get_ExpectedTableOfContents(tagSAFEARRAY * *)

- ea: `0x18003ad90`
- end: `0x18003afa8`
- name: `?get_ExpectedTableOfContents@CMsftDiscFormat2TrackAtOnce@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `536`
- prototype: `__int64 __fastcall(CMsftDiscFormat2TrackAtOnce *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002fc8`
- `0x180016778`
- `0x18001cb0c`
- `0x18003ad90`
- `0x180049832`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18003af03`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18003af03`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2TrackAtOnce::get_ExpectedTableOfContents(
        CMsftDiscFormat2TrackAtOnce *this,
        struct tagSAFEARRAY **a2)
{
  DWORD v2; // ebx
  unsigned int v5; // edi
  int v6; // eax
  ULONG v7; // r14d
  SAFEARRAY *Vector; // rax
  struct tagSAFEARRAY *v9; // rbp
  const struct _GUID *v10; // r8
  SAFEARRAY *v12; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  v12 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 42), 93, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
    }
    v2 = -2147467261;
    v5 = 0x80000000;
    goto LABEL_32;
  }
  *a2 = 0;
  if ( *((_WORD *)this + 84) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 42), 94, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
    }
    v2 = -1062599424;
LABEL_25:
    v5 = -2136342528;
    goto LABEL_32;
  }
  if ( !*((_WORD *)this + 100) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 42), 95, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
    }
    v2 = -1062599422;
    goto LABEL_25;
  }
  v6 = *((_DWORD *)this + 71);
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 42), 96, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
    }
    v2 = -1062599419;
    goto LABEL_25;
  }
  v7 = 8 * v6 + 12;
  Vector = SafeArrayCreateVector(0x11u, 0, v7);
  v12 = Vector;
  v9 = Vector;
  if ( Vector )
  {
    memcpy_0(Vector->pvData, (char *)this + 288, v7);
    *a2 = v9;
    return v2;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 42), 97, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
  }
  v2 = -2147024882;
  v5 = -2147024896;
LABEL_32:
  Imapi2Utility::SafeArrayDestroyAndNull((Imapi2Utility *)&v12, a2);
  if ( v5 == -2136342528 )
    Imapi2Utility::SetErrorDescription(v2, (__int64)&CLSID_MsftDiscFormat2TrackAtOnce, v10);
  return v2;
}

```

## disassembly

```asm
0x18003ad90  mov     [rsp+arg_0], rbx
0x18003ad95  mov     [rsp+arg_10], rbp
0x18003ad9a  push    rsi
0x18003ad9b  push    rdi
0x18003ad9c  push    r14
0x18003ad9e  sub     rsp, 20h
0x18003ada2  xor     ebx, ebx
0x18003ada4  mov     rsi, rdx
0x18003ada7  mov     [rsp+38h+arg_8], rbx
0x18003adac  mov     rdi, rcx
0x18003adaf  test    rdx, rdx
0x18003adb2  jnz     short loc_18003ADFE
0x18003adb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003adbb  lea     rax, WPP_GLOBAL_Control
0x18003adc2  cmp     rcx, rax
0x18003adc5  jz      short loc_18003ADEF
0x18003adc7  test    byte ptr [rcx+15Ch], 4
0x18003adce  jz      short loc_18003ADEF
0x18003add0  cmp     byte ptr [rcx+159h], 3
0x18003add7  jb      short loc_18003ADEF
0x18003add9  mov     rcx, [rcx+150h]
0x18003ade0  lea     edx, [rsi+5Dh]
0x18003ade3  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x18003adea  call    WPP_SF_
0x18003adef  mov     ebx, 80004003h
0x18003adf4  mov     edi, 80000000h
0x18003adf9  jmp     loc_18003AF5B
0x18003adfe  mov     [rdx], rbx
0x18003ae01  cmp     [rcx+0A8h], bx
0x18003ae08  jz      short loc_18003AE51
0x18003ae0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ae11  lea     rax, WPP_GLOBAL_Control
0x18003ae18  cmp     rcx, rax
0x18003ae1b  jz      short loc_18003AE47
0x18003ae1d  test    byte ptr [rcx+15Ch], 4
0x18003ae24  jz      short loc_18003AE47
0x18003ae26  cmp     byte ptr [rcx+159h], 3
0x18003ae2d  jb      short loc_18003AE47
0x18003ae2f  mov     rcx, [rcx+150h]
0x18003ae36  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x18003ae3d  mov     edx, 5Eh ; '^'
0x18003ae42  call    WPP_SF_
0x18003ae47  mov     ebx, 0C0AA0500h
0x18003ae4c  jmp     loc_18003AEEA
0x18003ae51  cmp     [rcx+0C8h], bx
0x18003ae58  jnz     short loc_18003AE9E
0x18003ae5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ae61  lea     rax, WPP_GLOBAL_Control
0x18003ae68  cmp     rcx, rax
0x18003ae6b  jz      short loc_18003AE97
0x18003ae6d  test    byte ptr [rcx+15Ch], 4
0x18003ae74  jz      short loc_18003AE97
0x18003ae76  cmp     byte ptr [rcx+159h], 3
0x18003ae7d  jb      short loc_18003AE97
0x18003ae7f  mov     rcx, [rcx+150h]
0x18003ae86  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x18003ae8d  mov     edx, 5Fh ; '_'
0x18003ae92  call    WPP_SF_
0x18003ae97  mov     ebx, 0C0AA0502h
0x18003ae9c  jmp     short loc_18003AEEA
0x18003ae9e  mov     eax, [rcx+11Ch]
0x18003aea4  test    eax, eax
0x18003aea6  jnz     short loc_18003AEF1
0x18003aea8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003aeaf  lea     rax, WPP_GLOBAL_Control
0x18003aeb6  cmp     rcx, rax
0x18003aeb9  jz      short loc_18003AEE5
0x18003aebb  test    byte ptr [rcx+15Ch], 4
0x18003aec2  jz      short loc_18003AEE5
0x18003aec4  cmp     byte ptr [rcx+159h], 3
0x18003aecb  jb      short loc_18003AEE5
0x18003aecd  mov     rcx, [rcx+150h]
0x18003aed4  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x18003aedb  mov     edx, 60h ; '`'
0x18003aee0  call    WPP_SF_
0x18003aee5  mov     ebx, 0C0AA0505h
0x18003aeea  mov     edi, 80AA0000h
0x18003aeef  jmp     short loc_18003AF5B
0x18003aef1  lea     r14d, ds:0Ch[rax*8]
0x18003aef9  mov     ecx, 11h; vt
0x18003aefe  mov     r8d, r14d; cElements
0x18003af01  xor     edx, edx; lLbound
0x18003af03  call    cs:__imp_SafeArrayCreateVector
0x18003af09  mov     [rsp+38h+arg_8], rax
0x18003af0e  mov     rbp, rax
0x18003af11  test    rax, rax
0x18003af14  jnz     short loc_18003AF7D
0x18003af16  mov     rcx, cs:WPP_GLOBAL_Control
0x18003af1d  lea     rax, WPP_GLOBAL_Control
0x18003af24  cmp     rcx, rax
0x18003af27  jz      short loc_18003AF51
0x18003af29  test    byte ptr [rcx+15Ch], 4
0x18003af30  jz      short loc_18003AF51
0x18003af32  cmp     byte ptr [rcx+159h], 3
0x18003af39  jb      short loc_18003AF51
0x18003af3b  mov     rcx, [rcx+150h]
0x18003af42  lea     edx, [rbp+61h]
0x18003af45  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x18003af4c  call    WPP_SF_
0x18003af51  mov     ebx, 8007000Eh
0x18003af56  mov     edi, 80070000h
0x18003af5b  lea     rcx, [rsp+38h+arg_8]; this
0x18003af60  call    ?SafeArrayDestroyAndNull@Imapi2Utility@@YAXAEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::SafeArrayDestroyAndNull(tagSAFEARRAY * &)
0x18003af65  cmp     edi, 80AA0000h
0x18003af6b  jnz     short loc_18003AF93
0x18003af6d  lea     rdx, CLSID_MsftDiscFormat2TrackAtOnce; int
0x18003af74  mov     ecx, ebx; dwMessageId
0x18003af76  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x18003af7b  jmp     short loc_18003AF93
0x18003af7d  mov     rcx, [rax+10h]; void *
0x18003af81  lea     rdx, [rdi+120h]; Src
0x18003af88  mov     r8d, r14d; Size
0x18003af8b  call    memcpy_0
0x18003af90  mov     [rsi], rbp
0x18003af93  mov     rbp, [rsp+38h+arg_10]
0x18003af98  mov     eax, ebx
0x18003af9a  mov     rbx, [rsp+38h+arg_0]
0x18003af9f  add     rsp, 20h
0x18003afa3  pop     r14
0x18003afa5  pop     rdi
0x18003afa6  pop     rsi
0x18003afa7  retn
```
