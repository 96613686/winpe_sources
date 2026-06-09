# Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::CreateInAndOutStreamsFromUtf8(uchar const *,ulong)

- ea: `0x14001985c`
- end: `0x140019b5b`
- name: `?CreateInAndOutStreamsFromUtf8@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBEK@Z`
- size: `767`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001a0b8`

## callees

- `0x14000b0f4`
- `0x14001985c`
- `0x140069010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1400198ca`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x140019902`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1400198ca`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x140019902`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x140019a74`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x140019a74`
- `XmlLite!CreateXmlReader` at `0x1400199ed`
- `XmlLite!CreateXmlReader` at `0x1400199ed`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x140019966`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x140019ab5`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x140019966`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x140019ab5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::CreateInAndOutStreamsFromUtf8(
        Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser *this,
        const char *a2,
        int a3)
{
  HRESULT XmlReader; // ebx
  __int64 v6; // rdx
  char *v7; // rax
  const BYTE *v8; // rbx
  char *v9; // rsi
  const char *i; // rcx
  char *v11; // rax
  UINT v12; // r14d
  unsigned __int64 v13; // rsi
  IStream *v14; // rbx
  __int64 v15; // rcx
  _QWORD *v16; // rsi
  IStream *v17; // rbx
  __int64 v18; // rcx
  int pwszBaseUri; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a2 )
  {
    XmlReader = -2147024809;
    v6 = 354;
    goto LABEL_45;
  }
  if ( *((_QWORD *)this + 9) )
  {
    XmlReader = -2147024809;
    v6 = 355;
    goto LABEL_45;
  }
  if ( !a3 && a2[0xFFFFFFFFLL] )
  {
    XmlReader = -2147024809;
    v6 = 356;
    goto LABEL_45;
  }
  v7 = strstr(a2, "<SyncBody");
  v8 = (const BYTE *)v7;
  if ( !v7 )
  {
    XmlReader = -2147024809;
    v6 = 369;
    goto LABEL_45;
  }
  v9 = 0;
  for ( i = v7; ; i = v11 + 1 )
  {
    v11 = strstr(i, "</SyncML>");
    if ( !v11 )
      break;
    v9 = v11;
  }
  if ( a2 >= (const char *)v8 )
  {
    XmlReader = -2147024809;
    v6 = 380;
    goto LABEL_45;
  }
  if ( v8 >= (const BYTE *)v9 )
  {
    XmlReader = -2147024809;
    v6 = 381;
    goto LABEL_45;
  }
  v12 = (_DWORD)v8 - (_DWORD)a2;
  if ( (unsigned __int64)(v8 - (const BYTE *)a2) > 0xFFFFFFFF )
  {
    v6 = 387;
LABEL_44:
    XmlReader = -2147024362;
    goto LABEL_45;
  }
  v13 = v9 - (char *)v8;
  if ( v13 > 0xFFFFFFFF )
  {
    v6 = 393;
    goto LABEL_44;
  }
  v14 = SHCreateMemStream(v8, v13);
  v15 = *((_QWORD *)this + 9);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  *((_QWORD *)this + 9) = v14;
  if ( v14 )
  {
    XmlReader = (*(__int64 (__fastcall **)(IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v14 + 40LL))(v14, 0, 0, 0);
    if ( XmlReader >= 0 )
    {
      v16 = (_QWORD *)((char *)this + 64);
      XmlReader = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, (void **)this + 8, 0);
      if ( XmlReader >= 0 )
      {
        XmlReader = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v16 + 40LL))(*v16, 4);
        if ( XmlReader >= 0 )
        {
          XmlReader = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v16 + 40LL))(*v16, 1, 1);
          if ( XmlReader >= 0 )
          {
            XmlReader = CreateXmlReaderInputWithEncodingName(
                          *((IUnknown **)this + 9),
                          0,
                          L"UTF-8",
                          0,
                          0,
                          (IXmlReaderInput **)this + 10);
            if ( XmlReader >= 0 )
            {
              XmlReader = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v16 + 24LL))(
                            *v16,
                            *((_QWORD *)this + 10));
              if ( XmlReader >= 0 )
              {
                v17 = SHCreateMemStream((const BYTE *)a2, v12);
                v18 = *((_QWORD *)this + 3);
                if ( v18 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
                *((_QWORD *)this + 3) = v17;
                if ( v17 )
                {
                  XmlReader = (*(__int64 (__fastcall **)(IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v17 + 40LL))(
                                v17,
                                v12,
                                0,
                                0);
                  if ( XmlReader >= 0 )
                    return 0;
                  v6 = 441;
                }
                else
                {
                  XmlReader = -2147024882;
                  v6 = 434;
                }
              }
              else
              {
                v6 = 428;
              }
            }
            else
            {
              v6 = 425;
            }
          }
          else
          {
            v6 = 416;
          }
        }
        else
        {
          v6 = 411;
        }
      }
      else
      {
        v6 = 406;
      }
    }
    else
    {
      v6 = 403;
    }
  }
  else
  {
    XmlReader = -2147024882;
    v6 = 398;
  }
LABEL_45:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
    (const char *)(unsigned int)XmlReader,
    pwszBaseUri);
  return (unsigned int)XmlReader;
}

```

## disassembly

```asm
0x14001985c  mov     [rsp+arg_0], rbx
0x140019861  mov     [rsp+arg_10], rbp
0x140019866  push    rsi
0x140019867  push    rdi
0x140019868  push    r13
0x14001986a  push    r14
0x14001986c  push    r15
0x14001986e  sub     rsp, 30h
0x140019872  mov     rbp, rdx
0x140019875  mov     rdi, rcx
0x140019878  test    rdx, rdx
0x14001987b  jnz     short loc_14001988C
0x14001987d  mov     ebx, 80070057h
0x140019882  mov     edx, 162h
0x140019887  jmp     loc_140019B2D
0x14001988c  cmp     qword ptr [rcx+48h], 0
0x140019891  jz      short loc_1400198A2
0x140019893  mov     ebx, 80070057h
0x140019898  mov     edx, 163h
0x14001989d  jmp     loc_140019B2D
0x1400198a2  test    r8d, r8d
0x1400198a5  jnz     short loc_1400198C0
0x1400198a7  lea     eax, [r8-1]
0x1400198ab  cmp     [rax+rdx], r8b
0x1400198af  jz      short loc_1400198C0
0x1400198b1  mov     ebx, 80070057h
0x1400198b6  mov     edx, 164h
0x1400198bb  jmp     loc_140019B2D
0x1400198c0  lea     rdx, aSyncbody_0; "<SyncBody"
0x1400198c7  mov     rcx, rbp; Str
0x1400198ca  call    cs:__imp_strstr
0x1400198d1  nop     dword ptr [rax+rax+00h]
0x1400198d6  mov     rbx, rax
0x1400198d9  test    rax, rax
0x1400198dc  jnz     short loc_1400198ED
0x1400198de  mov     ebx, 80070057h
0x1400198e3  mov     edx, 171h
0x1400198e8  jmp     loc_140019B2D
0x1400198ed  xor     esi, esi
0x1400198ef  mov     rcx, rbx
0x1400198f2  jmp     short loc_1400198FB
0x1400198f4  mov     rsi, rax
0x1400198f7  lea     rcx, [rax+1]; Str
0x1400198fb  lea     rdx, aSyncml_0; "</SyncML>"
0x140019902  call    cs:__imp_strstr
0x140019909  nop     dword ptr [rax+rax+00h]
0x14001990e  test    rax, rax
0x140019911  jnz     short loc_1400198F4
0x140019913  cmp     rbp, rbx
0x140019916  jb      short loc_140019927
0x140019918  mov     ebx, 80070057h
0x14001991d  mov     edx, 17Ch
0x140019922  jmp     loc_140019B2D
0x140019927  cmp     rbx, rsi
0x14001992a  jb      short loc_14001993B
0x14001992c  mov     ebx, 80070057h
0x140019931  mov     edx, 17Dh
0x140019936  jmp     loc_140019B2D
0x14001993b  mov     r14, rbx
0x14001993e  sub     r14, rbp
0x140019941  mov     eax, 0FFFFFFFFh
0x140019946  cmp     r14, rax
0x140019949  jbe     short loc_140019955
0x14001994b  mov     edx, 183h
0x140019950  jmp     loc_140019B28
0x140019955  sub     rsi, rbx
0x140019958  cmp     rsi, rax
0x14001995b  ja      loc_140019B23
0x140019961  mov     edx, esi; cbInit
0x140019963  mov     rcx, rbx; pInit
0x140019966  call    cs:__imp_SHCreateMemStream
0x14001996d  nop     dword ptr [rax+rax+00h]
0x140019972  mov     rbx, rax
0x140019975  mov     rcx, [rdi+48h]
0x140019979  test    rcx, rcx
0x14001997c  jz      short loc_14001998A
0x14001997e  mov     rdx, [rcx]
0x140019981  mov     rax, [rdx+10h]
0x140019985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001998a  mov     [rdi+48h], rbx
0x14001998e  test    rbx, rbx
0x140019991  jnz     short loc_1400199A2
0x140019993  mov     ebx, 8007000Eh
0x140019998  mov     edx, 18Eh
0x14001999d  jmp     loc_140019B2D
0x1400199a2  mov     dword ptr [rsp+58h+arg_8], 0
0x1400199aa  xor     r13d, r13d
0x1400199ad  mov     dword ptr [rsp+58h+arg_8+4], r13d
0x1400199b2  mov     rax, [rbx]
0x1400199b5  xor     r9d, r9d
0x1400199b8  xor     r8d, r8d
0x1400199bb  mov     rdx, [rsp+58h+arg_8]
0x1400199c0  mov     rcx, rbx
0x1400199c3  mov     rax, [rax+28h]
0x1400199c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400199cc  mov     ebx, eax
0x1400199ce  test    eax, eax
0x1400199d0  jns     short loc_1400199DC
0x1400199d2  mov     edx, 193h
0x1400199d7  jmp     loc_140019B2D
0x1400199dc  lea     rsi, [rdi+40h]
0x1400199e0  xor     r8d, r8d; pMalloc
0x1400199e3  mov     rdx, rsi; ppvObject
0x1400199e6  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1400199ed  call    cs:__imp_CreateXmlReader
0x1400199f4  nop     dword ptr [rax+rax+00h]
0x1400199f9  mov     ebx, eax
0x1400199fb  test    eax, eax
0x1400199fd  jns     short loc_140019A09
0x1400199ff  mov     edx, 196h
0x140019a04  jmp     loc_140019B2D
0x140019a09  mov     rcx, [rsi]
0x140019a0c  mov     rax, [rcx]
0x140019a0f  xor     r8d, r8d
0x140019a12  lea     edx, [r8+4]
0x140019a16  mov     rax, [rax+28h]
0x140019a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019a1f  mov     ebx, eax
0x140019a21  test    eax, eax
0x140019a23  jns     short loc_140019A2F
0x140019a25  mov     edx, 19Bh
0x140019a2a  jmp     loc_140019B2D
0x140019a2f  mov     rcx, [rsi]
0x140019a32  mov     rax, [rcx]
0x140019a35  mov     edx, 1
0x140019a3a  mov     r8d, edx
0x140019a3d  mov     rax, [rax+28h]
0x140019a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019a46  mov     ebx, eax
0x140019a48  test    eax, eax
0x140019a4a  jns     short loc_140019A56
0x140019a4c  mov     edx, 1A0h
0x140019a51  jmp     loc_140019B2D
0x140019a56  lea     r15, [rdi+50h]
0x140019a5a  mov     [rsp+58h+ppInput], r15; ppInput
0x140019a5f  mov     [rsp+58h+pwszBaseUri], r13; pwszBaseUri
0x140019a64  xor     r9d, r9d; fEncodingHint
0x140019a67  lea     r8, pwszEncodingName; "UTF-8"
0x140019a6e  xor     edx, edx; pMalloc
0x140019a70  mov     rcx, [rdi+48h]; pInputStream
0x140019a74  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x140019a7b  nop     dword ptr [rax+rax+00h]
0x140019a80  mov     ebx, eax
0x140019a82  test    eax, eax
0x140019a84  jns     short loc_140019A90
0x140019a86  mov     edx, 1A9h
0x140019a8b  jmp     loc_140019B2D
0x140019a90  mov     rcx, [rsi]
0x140019a93  mov     rax, [rcx]
0x140019a96  mov     rdx, [r15]
0x140019a99  mov     rax, [rax+18h]
0x140019a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019aa2  mov     ebx, eax
0x140019aa4  test    eax, eax
0x140019aa6  jns     short loc_140019AAF
0x140019aa8  mov     edx, 1ACh
0x140019aad  jmp     short loc_140019B2D
0x140019aaf  mov     edx, r14d; cbInit
0x140019ab2  mov     rcx, rbp; pInit
0x140019ab5  call    cs:__imp_SHCreateMemStream
0x140019abc  nop     dword ptr [rax+rax+00h]
0x140019ac1  mov     rbx, rax
0x140019ac4  mov     rcx, [rdi+18h]
0x140019ac8  test    rcx, rcx
0x140019acb  jz      short loc_140019AD9
0x140019acd  mov     rdx, [rcx]
0x140019ad0  mov     rax, [rdx+10h]
0x140019ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019ad9  mov     [rdi+18h], rbx
0x140019add  test    rbx, rbx
0x140019ae0  jnz     short loc_140019AEE
0x140019ae2  mov     ebx, 8007000Eh
0x140019ae7  mov     edx, 1B2h
0x140019aec  jmp     short loc_140019B2D
0x140019aee  mov     dword ptr [rsp+58h+arg_8], r14d
0x140019af3  mov     dword ptr [rsp+58h+arg_8+4], r13d
0x140019af8  mov     rax, [rbx]
0x140019afb  xor     r9d, r9d
0x140019afe  xor     r8d, r8d
0x140019b01  mov     rdx, [rsp+58h+arg_8]
0x140019b06  mov     rcx, rbx
0x140019b09  mov     rax, [rax+28h]
0x140019b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019b12  mov     ebx, eax
0x140019b14  test    eax, eax
0x140019b16  jns     short loc_140019B1F
0x140019b18  mov     edx, 1B9h
0x140019b1d  jmp     short loc_140019B2D
0x140019b1f  xor     eax, eax
0x140019b21  jmp     short loc_140019B43
0x140019b23  mov     edx, 189h; void *
0x140019b28  mov     ebx, 80070216h
0x140019b2d  mov     r9d, ebx; char *
0x140019b30  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140019b37  mov     rcx, [rsp+58h]; this
0x140019b3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019b41  mov     eax, ebx
0x140019b43  mov     rbx, [rsp+58h+arg_0]
0x140019b48  mov     rbp, [rsp+58h+arg_10]
0x140019b4d  add     rsp, 30h
0x140019b51  pop     r15
0x140019b53  pop     r14
0x140019b55  pop     r13
0x140019b57  pop     rdi
0x140019b58  pop     rsi
0x140019b59  retn
```
