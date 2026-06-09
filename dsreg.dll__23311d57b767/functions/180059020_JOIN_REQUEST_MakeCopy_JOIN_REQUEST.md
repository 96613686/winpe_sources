# _JOIN_REQUEST::MakeCopy(_JOIN_REQUEST * *)

- ea: `0x180059020`
- end: `0x180059532`
- name: `?MakeCopy@_JOIN_REQUEST@@QEAAJPEAPEAU1@@Z`
- size: `1298`
- prototype: `__int64 __fastcall(_JOIN_REQUEST *__hidden this, struct _JOIN_REQUEST **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180057c74`

## callees

- `0x1800084f4`
- `0x180011fc0`
- `0x1800307c4`
- `0x18003334c`
- `0x18004651c`
- `0x1800518a8`
- `0x18005541c`
- `0x180055da4`
- `0x180059020`
- `0x18005f5c4`
- `0x180074278`
- `0x18008a978`
- `0x18008af7c`

## string_xrefs

- `0x180059268`: `CopyStringNullSafeW`
- `0x180059046`: `_JOIN_REQUEST::MakeCopy`
- `0x180059060`: `_JOIN_REQUEST::MakeCopy`
- `0x180059131`: `_JOIN_REQUEST::MakeCopy`
- `0x1800594f4`: `_JOIN_REQUEST::MakeCopy`
- `0x180059127`: `GeneratedKey::CopyTo(DeviceKey)`
- `0x180059163`: `ByteArray::CopyTo(DeviceCSR)`
- `0x180059186`: `ByteArray::CopyTo(DevicePublicKey)`
- `0x1800591a5`: `GeneratedKey::CopyTo(RaKey)`
- `0x1800591c8`: `ByteArray::CopyTo(RaCSR)`
- `0x1800591ee`: `ByteArray::CopyTo(Software)`
- `0x180059214`: `ByteArray::CopyTo(TPM)`
- `0x180059240`: `ByteArray::CopyTo(KeyGuard)`
- `0x1800592eb`: `ByteArray::CopyTo(TransportKey)`
- `0x18005931a`: `ByteArray::CopyTo(TransportKeyAttestationStatement)`
- `0x180059349`: `ByteArray::CopyTo(TransportKeyAikCertificate)`
- `0x1800593f1`: `CopyDiscoveryMetadataContent`
- `0x180059419`: `CopyTokenProperties`
- `0x1800594e1`: `CopyVdiSettings`

## pseudocode

```c
__int64 __fastcall _JOIN_REQUEST::MakeCopy(_JOIN_REQUEST *this, struct _JOIN_REQUEST **a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // edx
  _JOIN_REQUEST *v6; // rax
  _JOIN_REQUEST *v7; // rax
  int v8; // eax
  const wchar_t *v9; // r8

  if ( a2 )
  {
    *a2 = 0;
    v6 = (_JOIN_REQUEST *)operator new(0x2D8u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v6 )
    {
      v7 = _JOIN_REQUEST::_JOIN_REQUEST(v6);
      *a2 = v7;
      if ( v7 )
      {
        *((_DWORD *)v7 + 156) = *((_DWORD *)this + 156);
        *((_DWORD *)*a2 + 157) = *((_DWORD *)this + 157);
        *((_DWORD *)*a2 + 158) = *((_DWORD *)this + 158);
        *((_DWORD *)*a2 + 159) = *((_DWORD *)this + 159);
        *((_DWORD *)*a2 + 160) = *((_DWORD *)this + 160);
        *((_QWORD *)*a2 + 84) = *((_QWORD *)this + 84);
        *((_DWORD *)*a2 + 166) = *((_DWORD *)this + 166);
        v8 = GeneratedKey::CopyTo(this, *a2);
        v4 = v8;
        if ( v8 >= 0 )
        {
          v8 = ByteArray::Assign(
                 (struct _JOIN_REQUEST *)((char *)*a2 + 24),
                 *((const unsigned __int8 **)this + 3),
                 *((_QWORD *)this + 4));
          v4 = v8;
          if ( v8 >= 0 )
          {
            v8 = ByteArray::Assign(
                   (struct _JOIN_REQUEST *)((char *)*a2 + 40),
                   *((const unsigned __int8 **)this + 5),
                   *((_QWORD *)this + 6));
            v4 = v8;
            if ( v8 >= 0 )
            {
              v8 = GeneratedKey::CopyTo(
                     (_JOIN_REQUEST *)((char *)this + 56),
                     (struct _JOIN_REQUEST *)((char *)*a2 + 56));
              v4 = v8;
              if ( v8 >= 0 )
              {
                v8 = ByteArray::Assign(
                       (struct _JOIN_REQUEST *)((char *)*a2 + 80),
                       *((const unsigned __int8 **)this + 10),
                       *((_QWORD *)this + 11));
                v4 = v8;
                if ( v8 >= 0 )
                {
                  v8 = ByteArray::Assign(
                         (struct _JOIN_REQUEST *)((char *)*a2 + 96),
                         *((const unsigned __int8 **)this + 12),
                         *((_QWORD *)this + 13));
                  v4 = v8;
                  if ( v8 >= 0 )
                  {
                    v8 = ByteArray::Assign(
                           (struct _JOIN_REQUEST *)((char *)*a2 + 112),
                           *((const unsigned __int8 **)this + 14),
                           *((_QWORD *)this + 15));
                    v4 = v8;
                    if ( v8 >= 0 )
                    {
                      v8 = ByteArray::Assign(
                             (struct _JOIN_REQUEST *)((char *)*a2 + 128),
                             *((const unsigned __int8 **)this + 16),
                             *((_QWORD *)this + 17));
                      v4 = v8;
                      if ( v8 >= 0 )
                      {
                        v8 = CopyStringNullSafeW(*((const unsigned __int16 **)this + 18), (unsigned __int16 **)*a2 + 18);
                        v4 = v8;
                        if ( v8 >= 0 )
                        {
                          v8 = CopyStringNullSafeW(
                                 *((const unsigned __int16 **)this + 19),
                                 (unsigned __int16 **)*a2 + 19);
                          v4 = v8;
                          if ( v8 >= 0 )
                          {
                            v8 = CopyStringNullSafeW(
                                   *((const unsigned __int16 **)this + 20),
                                   (unsigned __int16 **)*a2 + 20);
                            v4 = v8;
                            if ( v8 >= 0 )
                            {
                              v8 = CopyStringNullSafeW(
                                     *((const unsigned __int16 **)this + 21),
                                     (unsigned __int16 **)*a2 + 21);
                              v4 = v8;
                              if ( v8 >= 0 )
                              {
                                v8 = ByteArray::Assign(
                                       (struct _JOIN_REQUEST *)((char *)*a2 + 176),
                                       *((const unsigned __int8 **)this + 22),
                                       *((_QWORD *)this + 23));
                                v4 = v8;
                                if ( v8 < 0 )
                                {
                                  v9 = L"ByteArray::CopyTo(TransportKey)";
                                  goto LABEL_7;
                                }
                                v8 = ByteArray::Assign(
                                       (struct _JOIN_REQUEST *)((char *)*a2 + 192),
                                       *((const unsigned __int8 **)this + 24),
                                       *((_QWORD *)this + 25));
                                v4 = v8;
                                if ( v8 < 0 )
                                {
                                  v9 = L"ByteArray::CopyTo(TransportKeyAttestationStatement)";
                                  goto LABEL_7;
                                }
                                v8 = ByteArray::Assign(
                                       (struct _JOIN_REQUEST *)((char *)*a2 + 208),
                                       *((const unsigned __int8 **)this + 26),
                                       *((_QWORD *)this + 27));
                                v4 = v8;
                                if ( v8 < 0 )
                                {
                                  v9 = L"ByteArray::CopyTo(TransportKeyAikCertificate)";
                                  goto LABEL_7;
                                }
                                v8 = CopyStringNullSafeW(
                                       *((const unsigned __int16 **)this + 28),
                                       (unsigned __int16 **)*a2 + 28);
                                v4 = v8;
                                if ( v8 >= 0 )
                                {
                                  v8 = CopyStringNullSafeW(
                                         *((const unsigned __int16 **)this + 29),
                                         (unsigned __int16 **)*a2 + 29);
                                  v4 = v8;
                                  if ( v8 >= 0 )
                                  {
                                    v8 = CopyStringNullSafeW(
                                           *((const unsigned __int16 **)this + 30),
                                           (unsigned __int16 **)*a2 + 30);
                                    v4 = v8;
                                    if ( v8 >= 0 )
                                    {
                                      v8 = CopyStringNullSafeW(
                                             *((const unsigned __int16 **)this + 31),
                                             (unsigned __int16 **)*a2 + 31);
                                      v4 = v8;
                                      if ( v8 >= 0 )
                                      {
                                        v8 = CopyDiscoveryMetadataContent(
                                               (_JOIN_REQUEST *)((char *)this + 272),
                                               (struct _JOIN_REQUEST *)((char *)*a2 + 272));
                                        v4 = v8;
                                        if ( v8 < 0 )
                                        {
                                          v9 = L"CopyDiscoveryMetadataContent";
                                          goto LABEL_7;
                                        }
                                        v8 = CopyTokenProperties(
                                               (_JOIN_REQUEST *)((char *)this + 528),
                                               (struct _JOIN_REQUEST *)((char *)*a2 + 528));
                                        v4 = v8;
                                        if ( v8 < 0 )
                                        {
                                          v9 = L"CopyTokenProperties";
                                          goto LABEL_7;
                                        }
                                        v8 = CopyStringNullSafeW(
                                               *((const unsigned __int16 **)this + 77),
                                               (unsigned __int16 **)*a2 + 77);
                                        v4 = v8;
                                        if ( v8 >= 0 )
                                        {
                                          v8 = CopyStringNullSafeW(
                                                 *((const unsigned __int16 **)this + 81),
                                                 (unsigned __int16 **)*a2 + 81);
                                          v4 = v8;
                                          if ( v8 >= 0 )
                                          {
                                            v8 = CopyStringNullSafeW(
                                                   *((const unsigned __int16 **)this + 82),
                                                   (unsigned __int16 **)*a2 + 82);
                                            v4 = v8;
                                            if ( v8 >= 0 )
                                            {
                                              v8 = CopyStringNullSafeW(
                                                     *((const unsigned __int16 **)this + 85),
                                                     (unsigned __int16 **)*a2 + 85);
                                              v4 = v8;
                                              if ( v8 >= 0 )
                                              {
                                                v8 = CopyStringNullSafeW(
                                                       *((const unsigned __int16 **)this + 86),
                                                       (unsigned __int16 **)*a2 + 86);
                                                v4 = v8;
                                                if ( v8 >= 0 )
                                                {
                                                  v8 = CopyVdiSettings(
                                                         (_JOIN_REQUEST *)((char *)this + 696),
                                                         (struct _JOIN_REQUEST *)((char *)*a2 + 696));
                                                  v4 = v8;
                                                  if ( v8 >= 0 )
                                                    return v4;
                                                  v9 = L"CopyVdiSettings";
                                                  goto LABEL_7;
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                        v9 = L"CopyStringNullSafeW";
                      }
                      else
                      {
                        v9 = L"ByteArray::CopyTo(KeyGuard)";
                      }
                    }
                    else
                    {
                      v9 = L"ByteArray::CopyTo(TPM)";
                    }
                  }
                  else
                  {
                    v9 = L"ByteArray::CopyTo(Software)";
                  }
                }
                else
                {
                  v9 = L"ByteArray::CopyTo(RaCSR)";
                }
              }
              else
              {
                v9 = L"GeneratedKey::CopyTo(RaKey)";
              }
            }
            else
            {
              v9 = L"ByteArray::CopyTo(DevicePublicKey)";
            }
          }
          else
          {
            v9 = L"ByteArray::CopyTo(DeviceCSR)";
          }
        }
        else
        {
          v9 = L"GeneratedKey::CopyTo(DeviceKey)";
        }
LABEL_7:
        Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"_JOIN_REQUEST::MakeCopy", v9, (unsigned int)v8);
        goto LABEL_50;
      }
    }
    else
    {
      *a2 = 0;
    }
    v4 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"_JOIN_REQUEST::MakeCopy");
    goto LABEL_50;
  }
  v4 = -2147024809;
  Logger::TraceError(L"%s: \"%s\" should not be null.", L"_JOIN_REQUEST::MakeCopy", L"ppDest");
  Logger::WriteNullOrEmptyParameterFailureEvent(L"_JOIN_REQUEST::MakeCopy", L"ppDest");
LABEL_50:
  if ( *a2 )
    _JOIN_REQUEST::`scalar deleting destructor'(*a2, v5);
  *a2 = 0;
  return v4;
}

```

## disassembly

```asm
0x180059020  mov     [rsp+arg_0], rbx
0x180059025  mov     [rsp+arg_10], rsi
0x18005902a  push    rdi
0x18005902b  sub     rsp, 20h
0x18005902f  mov     rsi, rdx
0x180059032  mov     rdi, rcx
0x180059035  test    rdx, rdx
0x180059038  jnz     short loc_180059071
0x18005903a  lea     r8, aPpdest; "ppDest"
0x180059041  mov     ebx, 80070057h
0x180059046  lea     rdx, aJoinRequestMak; "_JOIN_REQUEST::MakeCopy"
0x18005904d  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180059054  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180059059  lea     rdx, aPpdest; "ppDest"
0x180059060  lea     rcx, aJoinRequestMak; "_JOIN_REQUEST::MakeCopy"
0x180059067  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18005906c  jmp     loc_18005950C
0x180059071  mov     qword ptr [rdx], 0
0x180059078  mov     ecx, 2D8h; unsigned __int64
0x18005907d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180059084  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180059089  mov     [rsp+28h+arg_8], rax
0x18005908e  test    rax, rax
0x180059091  jz      loc_1800594ED
0x180059097  mov     rcx, rax; this
0x18005909a  call    ??0_JOIN_REQUEST@@QEAA@XZ; _JOIN_REQUEST::_JOIN_REQUEST(void)
0x18005909f  mov     [rsi], rax
0x1800590a2  mov     rcx, rax
0x1800590a5  test    rax, rax
0x1800590a8  jz      loc_1800594F4
0x1800590ae  mov     eax, [rdi+270h]
0x1800590b4  mov     [rcx+270h], eax
0x1800590ba  mov     eax, [rdi+274h]
0x1800590c0  mov     rcx, [rsi]
0x1800590c3  mov     [rcx+274h], eax
0x1800590c9  mov     eax, [rdi+278h]
0x1800590cf  mov     rcx, [rsi]
0x1800590d2  mov     [rcx+278h], eax
0x1800590d8  mov     eax, [rdi+27Ch]
0x1800590de  mov     rcx, [rsi]
0x1800590e1  mov     [rcx+27Ch], eax
0x1800590e7  mov     rcx, [rsi]
0x1800590ea  mov     eax, [rdi+280h]
0x1800590f0  mov     [rcx+280h], eax
0x1800590f6  mov     rcx, [rsi]
0x1800590f9  mov     rax, [rdi+2A0h]
0x180059100  mov     [rcx+2A0h], rax
0x180059107  mov     rcx, [rsi]
0x18005910a  mov     eax, [rdi+298h]
0x180059110  mov     [rcx+298h], eax
0x180059116  mov     rcx, rdi; this
0x180059119  mov     rdx, [rsi]; struct GeneratedKey *
0x18005911c  call    ?CopyTo@GeneratedKey@@QEBAJAEAV1@@Z; GeneratedKey::CopyTo(GeneratedKey &)
0x180059121  mov     ebx, eax
0x180059123  test    eax, eax
0x180059125  jns     short loc_180059149
0x180059127  lea     r8, aGeneratedkeyCo_1; "GeneratedKey::CopyTo(DeviceKey)"
0x18005912e  mov     r9d, eax
0x180059131  lea     rdx, aJoinRequestMak; "_JOIN_REQUEST::MakeCopy"
0x180059138  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005913f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180059144  jmp     loc_18005950C
0x180059149  mov     rcx, [rsi]
0x18005914c  mov     r8, [rdi+20h]; unsigned __int64
0x180059150  add     rcx, 18h; this
0x180059154  mov     rdx, [rdi+18h]; unsigned __int8 *
0x180059158  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x18005915d  mov     ebx, eax
0x18005915f  test    eax, eax
0x180059161  jns     short loc_18005916C
0x180059163  lea     r8, aBytearrayCopyt_7; "ByteArray::CopyTo(DeviceCSR)"
0x18005916a  jmp     short loc_18005912E
0x18005916c  mov     rcx, [rsi]
0x18005916f  mov     r8, [rdi+30h]; unsigned __int64
0x180059173  add     rcx, 28h ; '('; this
0x180059177  mov     rdx, [rdi+28h]; unsigned __int8 *
0x18005917b  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x180059180  mov     ebx, eax
0x180059182  test    eax, eax
0x180059184  jns     short loc_18005918F
0x180059186  lea     r8, aBytearrayCopyt_6; "ByteArray::CopyTo(DevicePublicKey)"
0x18005918d  jmp     short loc_18005912E
0x18005918f  mov     rdx, [rsi]
0x180059192  lea     rcx, [rdi+38h]; this
0x180059196  add     rdx, 38h ; '8'; struct GeneratedKey *
0x18005919a  call    ?CopyTo@GeneratedKey@@QEBAJAEAV1@@Z; GeneratedKey::CopyTo(GeneratedKey &)
0x18005919f  mov     ebx, eax
0x1800591a1  test    eax, eax
0x1800591a3  jns     short loc_1800591AE
0x1800591a5  lea     r8, aGeneratedkeyCo; "GeneratedKey::CopyTo(RaKey)"
0x1800591ac  jmp     short loc_18005912E
0x1800591ae  mov     rcx, [rsi]
0x1800591b1  mov     r8, [rdi+58h]; unsigned __int64
0x1800591b5  add     rcx, 50h ; 'P'; this
0x1800591b9  mov     rdx, [rdi+50h]; unsigned __int8 *
0x1800591bd  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x1800591c2  mov     ebx, eax
0x1800591c4  test    eax, eax
0x1800591c6  jns     short loc_1800591D4
0x1800591c8  lea     r8, aBytearrayCopyt_1; "ByteArray::CopyTo(RaCSR)"
0x1800591cf  jmp     loc_18005912E
0x1800591d4  mov     rcx, [rsi]
0x1800591d7  mov     r8, [rdi+68h]; unsigned __int64
0x1800591db  add     rcx, 60h ; '`'; this
0x1800591df  mov     rdx, [rdi+60h]; unsigned __int8 *
0x1800591e3  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x1800591e8  mov     ebx, eax
0x1800591ea  test    eax, eax
0x1800591ec  jns     short loc_1800591FA
0x1800591ee  lea     r8, aBytearrayCopyt; "ByteArray::CopyTo(Software)"
0x1800591f5  jmp     loc_18005912E
0x1800591fa  mov     rcx, [rsi]
0x1800591fd  mov     r8, [rdi+78h]; unsigned __int64
0x180059201  add     rcx, 70h ; 'p'; this
0x180059205  mov     rdx, [rdi+70h]; unsigned __int8 *
0x180059209  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x18005920e  mov     ebx, eax
0x180059210  test    eax, eax
0x180059212  jns     short loc_180059220
0x180059214  lea     r8, aBytearrayCopyt_4; "ByteArray::CopyTo(TPM)"
0x18005921b  jmp     loc_18005912E
0x180059220  mov     rcx, [rsi]
0x180059223  mov     r8, [rdi+88h]; unsigned __int64
0x18005922a  sub     rcx, 0FFFFFFFFFFFFFF80h; this
0x18005922e  mov     rdx, [rdi+80h]; unsigned __int8 *
0x180059235  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x18005923a  mov     ebx, eax
0x18005923c  test    eax, eax
0x18005923e  jns     short loc_18005924C
0x180059240  lea     r8, aBytearrayCopyt_8; "ByteArray::CopyTo(KeyGuard)"
0x180059247  jmp     loc_18005912E
0x18005924c  mov     rdx, [rsi]
0x18005924f  mov     rcx, [rdi+90h]; Source
0x180059256  add     rdx, 90h; unsigned __int16 **
0x18005925d  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x180059262  mov     ebx, eax
0x180059264  test    eax, eax
0x180059266  jns     short loc_180059274
0x180059268  lea     r8, aCopystringnull; "CopyStringNullSafeW"
0x18005926f  jmp     loc_18005912E
0x180059274  mov     rdx, [rsi]
0x180059277  mov     rcx, [rdi+98h]; Source
0x18005927e  add     rdx, 98h; unsigned __int16 **
0x180059285  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x18005928a  mov     ebx, eax
0x18005928c  test    eax, eax
0x18005928e  js      short loc_180059268
0x180059290  mov     rdx, [rsi]
0x180059293  mov     rcx, [rdi+0A0h]; Source
0x18005929a  add     rdx, 0A0h; unsigned __int16 **
0x1800592a1  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x1800592a6  mov     ebx, eax
0x1800592a8  test    eax, eax
0x1800592aa  js      short loc_180059268
0x1800592ac  mov     rdx, [rsi]
0x1800592af  mov     rcx, [rdi+0A8h]; Source
0x1800592b6  add     rdx, 0A8h; unsigned __int16 **
0x1800592bd  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x1800592c2  mov     ebx, eax
0x1800592c4  test    eax, eax
0x1800592c6  js      short loc_180059268
0x1800592c8  mov     rcx, [rsi]
0x1800592cb  mov     r8, [rdi+0B8h]; unsigned __int64
0x1800592d2  add     rcx, 0B0h; this
0x1800592d9  mov     rdx, [rdi+0B0h]; unsigned __int8 *
0x1800592e0  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x1800592e5  mov     ebx, eax
0x1800592e7  test    eax, eax
0x1800592e9  jns     short loc_1800592F7
0x1800592eb  lea     r8, aBytearrayCopyt_5; "ByteArray::CopyTo(TransportKey)"
0x1800592f2  jmp     loc_18005912E
0x1800592f7  mov     rcx, [rsi]
0x1800592fa  mov     r8, [rdi+0C8h]; unsigned __int64
0x180059301  add     rcx, 0C0h; this
0x180059308  mov     rdx, [rdi+0C0h]; unsigned __int8 *
0x18005930f  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x180059314  mov     ebx, eax
0x180059316  test    eax, eax
0x180059318  jns     short loc_180059326
0x18005931a  lea     r8, aBytearrayCopyt_0; "ByteArray::CopyTo(TransportKeyAttestati"...
0x180059321  jmp     loc_18005912E
0x180059326  mov     rcx, [rsi]
0x180059329  mov     r8, [rdi+0D8h]; unsigned __int64
0x180059330  add     rcx, 0D0h; this
0x180059337  mov     rdx, [rdi+0D0h]; unsigned __int8 *
0x18005933e  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x180059343  mov     ebx, eax
0x180059345  test    eax, eax
0x180059347  jns     short loc_180059355
0x180059349  lea     r8, aBytearrayCopyt_2; "ByteArray::CopyTo(TransportKeyAikCertif"...
0x180059350  jmp     loc_18005912E
0x180059355  mov     rdx, [rsi]
0x180059358  mov     rcx, [rdi+0E0h]; Source
0x18005935f  add     rdx, 0E0h; unsigned __int16 **
0x180059366  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x18005936b  mov     ebx, eax
0x18005936d  test    eax, eax
0x18005936f  js      loc_180059268
0x180059375  mov     rdx, [rsi]
0x180059378  mov     rcx, [rdi+0E8h]; Source
0x18005937f  add     rdx, 0E8h; unsigned __int16 **
0x180059386  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x18005938b  mov     ebx, eax
0x18005938d  test    eax, eax
0x18005938f  js      loc_180059268
0x180059395  mov     rdx, [rsi]
0x180059398  mov     rcx, [rdi+0F0h]; Source
0x18005939f  add     rdx, 0F0h; unsigned __int16 **
0x1800593a6  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x1800593ab  mov     ebx, eax
0x1800593ad  test    eax, eax
0x1800593af  js      loc_180059268
0x1800593b5  mov     rdx, [rsi]
0x1800593b8  mov     rcx, [rdi+0F8h]; Source
0x1800593bf  add     rdx, 0F8h; unsigned __int16 **
0x1800593c6  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x1800593cb  mov     ebx, eax
0x1800593cd  test    eax, eax
0x1800593cf  js      loc_180059268
0x1800593d5  mov     rdx, [rsi]
0x1800593d8  lea     rcx, [rdi+110h]; struct _DISCOVERY_METADATA *
0x1800593df  add     rdx, 110h; struct _DISCOVERY_METADATA *
0x1800593e6  call    ?CopyDiscoveryMetadataContent@@YAJPEBU_DISCOVERY_METADATA@@PEAU1@@Z; CopyDiscoveryMetadataContent(_DISCOVERY_METADATA const *,_DISCOVERY_METADATA *)
0x1800593eb  mov     ebx, eax
0x1800593ed  test    eax, eax
0x1800593ef  jns     short loc_1800593FD
0x1800593f1  lea     r8, aCopydiscoverym; "CopyDiscoveryMetadataContent"
0x1800593f8  jmp     loc_18005912E
0x1800593fd  mov     rdx, [rsi]
0x180059400  lea     rcx, [rdi+210h]; struct _DSREG_EXT_TOKEN_PROPERTIES_EX *
0x180059407  add     rdx, 210h; struct _DSREG_EXT_TOKEN_PROPERTIES_EX *
0x18005940e  call    ?CopyTokenProperties@@YAJPEBU_DSREG_EXT_TOKEN_PROPERTIES_EX@@PEAU1@@Z; CopyTokenProperties(_DSREG_EXT_TOKEN_PROPERTIES_EX const *,_DSREG_EXT_TOKEN_PROPERTIES_EX *)
0x180059413  mov     ebx, eax
0x180059415  test    eax, eax
0x180059417  jns     short loc_180059425
0x180059419  lea     r8, aCopytokenprope; "CopyTokenProperties"
0x180059420  jmp     loc_18005912E
0x180059425  mov     rdx, [rsi]
0x180059428  mov     rcx, [rdi+268h]; Source
0x18005942f  add     rdx, 268h; unsigned __int16 **
0x180059436  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x18005943b  mov     ebx, eax
0x18005943d  test    eax, eax
0x18005943f  js      loc_180059268
0x180059445  mov     rdx, [rsi]
0x180059448  mov     rcx, [rdi+288h]; Source
0x18005944f  add     rdx, 288h; unsigned __int16 **
0x180059456  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x18005945b  mov     ebx, eax
0x18005945d  test    eax, eax
0x18005945f  js      loc_180059268
0x180059465  mov     rdx, [rsi]
0x180059468  mov     rcx, [rdi+290h]; Source
0x18005946f  add     rdx, 290h; unsigned __int16 **
0x180059476  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x18005947b  mov     ebx, eax
0x18005947d  test    eax, eax
0x18005947f  js      loc_180059268
0x180059485  mov     rdx, [rsi]
0x180059488  mov     rcx, [rdi+2A8h]; Source
0x18005948f  add     rdx, 2A8h; unsigned __int16 **
0x180059496  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x18005949b  mov     ebx, eax
0x18005949d  test    eax, eax
0x18005949f  js      loc_180059268
0x1800594a5  mov     rdx, [rsi]
0x1800594a8  mov     rcx, [rdi+2B0h]; Source
0x1800594af  add     rdx, 2B0h; unsigned __int16 **
0x1800594b6  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x1800594bb  mov     ebx, eax
0x1800594bd  test    eax, eax
0x1800594bf  js      loc_180059268
0x1800594c5  mov     rdx, [rsi]
0x1800594c8  lea     rcx, [rdi+2B8h]; struct _VDI_SETTINGS *
0x1800594cf  add     rdx, 2B8h; struct _VDI_SETTINGS *
0x1800594d6  call    ?CopyVdiSettings@@YAJAEBU_VDI_SETTINGS@@AEAU1@@Z; CopyVdiSettings(_VDI_SETTINGS const &,_VDI_SETTINGS &)
0x1800594db  mov     ebx, eax
0x1800594dd  test    eax, eax
0x1800594df  jns     short loc_180059520
0x1800594e1  lea     r8, aCopyvdisetting; "CopyVdiSettings"
0x1800594e8  jmp     loc_18005912E
0x1800594ed  mov     qword ptr [rsi], 0
0x1800594f4  lea     rdx, aJoinRequestMak; "_JOIN_REQUEST::MakeCopy"
0x1800594fb  mov     ebx, 8007000Eh
0x180059500  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x180059507  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18005950c  mov     rcx, [rsi]; this
0x18005950f  test    rcx, rcx
0x180059512  jz      short loc_180059519
0x180059514  call    ??_G_JOIN_REQUEST@@QEAAPEAXI@Z; _JOIN_REQUEST::`scalar deleting destructor'(uint)
0x180059519  mov     qword ptr [rsi], 0
0x180059520  mov     rsi, [rsp+28h+arg_10]
0x180059525  mov     eax, ebx
0x180059527  mov     rbx, [rsp+28h+arg_0]
0x18005952c  add     rsp, 20h
0x180059530  pop     rdi
0x180059531  retn
```
