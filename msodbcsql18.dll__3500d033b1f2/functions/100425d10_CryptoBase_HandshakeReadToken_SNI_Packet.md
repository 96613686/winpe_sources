# CryptoBase::HandshakeReadToken(SNI_Packet *)

- ea: `0x100425d10`
- end: `0x1004262e0`
- name: `?HandshakeReadToken@CryptoBase@@IEAAKPEAVSNI_Packet@@@Z`
- size: `1488`
- prototype: `unsigned int __fastcall(CryptoBase *__hidden this, struct SNI_Packet *)`
- caller_count: `6`
- callee_count: `9`
- tags: ``

## callers

- `0x100425bcc`
- `0x1004262e8`
- `0x100427a90`
- `0x10042847c`
- `0x10042b580`
- `0x10042e940`

## callees

- `0x100412718`
- `0x10041847c`
- `0x100425d10`
- `0x10043a7c4`
- `0x10043a930`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100425f9c`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100425f9c`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x100425fe7`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x100425fe7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CryptoBase::HandshakeReadToken(CryptoBase *this, struct SNI_Packet *a2)
{
  int v3; // r12d
  unsigned int v4; // edi
  char *v5; // r15
  unsigned int v6; // esi
  unsigned int v7; // eax
  __int64 *v8; // rcx
  __int64 v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // eax
  int v12; // eax
  unsigned int v13; // edx
  unsigned int v14; // eax
  unsigned int v15; // r8d
  unsigned int v16; // esi
  _QWORD v18[2]; // [rsp+40h] [rbp-10h] BYREF
  char v19; // [rsp+90h] [rbp+40h] BYREF
  SNI_Packet *v20; // [rsp+98h] [rbp+48h] BYREF
  unsigned int v21; // [rsp+A0h] [rbp+50h] BYREF
  int v22; // [rsp+A8h] [rbp+58h] BYREF

  v20 = a2;
  v18[1] = -2;
  v18[0] = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 )
  {
    if ( off_1005E7B18[0] )
      bidScopeEnterW(v18, off_1005E7B18[0], *((unsigned int *)this + 11));
    a2 = v20;
  }
  v3 = 0;
  if ( *((_QWORD *)this + 7) )
  {
    if ( (bidGblFlags & 2) != 0 && off_1005E51B0[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
        bidID,
        0,
        2938880,
        off_1005E51B0[0],
        0);
    v4 = -2146893048;
    if ( (bidGblFlags & 2) != 0 && off_1005E51B8[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(0, 2941952, off_1005E51B8[0], *((unsigned int *)this + 6));
    }
    SNISetLastError(*((unsigned int *)this + 6), 2148074248LL, 50100);
    *((_DWORD *)this + 54) = 2;
    *((_DWORD *)this + 55) = 23;
  }
  else
  {
    while ( 2 )
    {
      v5 = 0;
      v22 = 0;
      v19 = 0;
      while ( 1 )
      {
        v6 = 0;
        if ( a2 )
        {
          v5 = (char *)(*((_QWORD *)a2 + 10) + *((unsigned int *)a2 + 24));
          v6 = *((_DWORD *)a2 + 22);
          v3 = *((_DWORD *)a2 + 23);
        }
        v7 = (*(__int64 (__fastcall **)(char *, _QWORD, unsigned int *, int *, int, char *))(*((_QWORD *)this + 28)
                                                                                           + 72LL))(
               v5,
               v6,
               &v21,
               &v22,
               v3,
               &v19);
        v4 = v7;
        if ( v7 != -2146893032 )
        {
          if ( v7 == -2146893048 )
          {
            if ( (bidGblFlags & 2) != 0 && off_1005E51C0[0] )
              bidTraceW(0, 2984960, off_1005E51C0[0], v21);
            if ( (bidGblFlags & 2) != 0 && off_1005E51C8[0] )
            {
              SniErrorIdFromStringId(0xC3B4u);
              bidTraceW(0, 2985984, off_1005E51C8[0], *((unsigned int *)this + 6));
            }
            SNISetLastError(*((unsigned int *)this + 6), 2148074248LL, 50100);
            *((_DWORD *)this + 54) = 2;
            *((_DWORD *)this + 55) = 24;
            goto LABEL_69;
          }
          if ( v6 >= v21 )
            break;
        }
        v8 = (__int64 *)*((_QWORD *)this + 1);
        v9 = *v8;
        if ( (*(_BYTE *)(*((_QWORD *)this + 4) + 236LL) & 1) != 0 )
        {
          if ( v20 )
            v10 = (*(__int64 (__fastcall **)(__int64 *, SNI_Packet *, _QWORD, __int64))(v9 + 16))(
                    v8,
                    v20,
                    v3 - v6,
                    0xFFFFFFFFLL);
          else
            v10 = (*(__int64 (__fastcall **)(__int64 *, SNI_Packet **, __int64))(v9 + 112))(v8, &v20, 0xFFFFFFFFLL);
          v4 = v10;
        }
        else
        {
          if ( v20 )
            v11 = (*(__int64 (__fastcall **)(__int64 *, SNI_Packet *, _QWORD, _QWORD))(v9 + 24))(v8, v20, v3 - v6, 0);
          else
            v11 = (*(__int64 (__fastcall **)(__int64 *, SNI_Packet **, _QWORD))(v9 + 120))(v8, &v20, 0);
          v4 = v11;
          if ( v11 == 997 )
          {
            v20 = 0;
            SNI_Conn::AddRef(*((_QWORD *)this + 4), 4);
            goto LABEL_69;
          }
        }
        if ( v4 )
        {
          if ( v4 != 997 )
          {
            *((_DWORD *)this + 54) = 2;
            *((_DWORD *)this + 55) = 27;
          }
          goto LABEL_69;
        }
        if ( (*((_BYTE *)this + 96) & 8) == 0 )
          _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 4) + 204LL));
        a2 = v20;
      }
      v12 = (*(__int64 (__fastcall **)(CryptoBase *))(*(_QWORD *)this + 192LL))(this);
      v13 = v21 + *((_DWORD *)this + 42) - v22;
      v14 = *((_DWORD *)this + 50) + *((_DWORD *)this + 51) + v12;
      _mm_lfence();
      if ( v13 > v14 )
      {
        v4 = -2146893048;
        if ( (bidGblFlags & 2) != 0 && off_1005E51D0[0] )
        {
          (*(void (__fastcall **)(CryptoBase *))(*(_QWORD *)this + 192LL))(this);
          bidTraceW(0, 3054592, off_1005E51D0[0], v21);
        }
        if ( (bidGblFlags & 2) != 0 && off_1005E51D8[0] )
        {
          SniErrorIdFromStringId(0xC3B4u);
          bidTraceW(0, 3055616, off_1005E51D8[0], *((unsigned int *)this + 6));
        }
        SNISetLastError(*((unsigned int *)this + 6), 2148074248LL, 50100);
        *((_DWORD *)this + 54) = 2;
        *((_DWORD *)this + 55) = 25;
      }
      else
      {
        memcpy_s((void *const)(*((_QWORD *)this + 19) + *((unsigned int *)this + 42)), v21 - v22, &v5[v22], v21 - v22);
        v15 = v21;
        *((_DWORD *)this + 42) += v21 - v22;
        v16 = v6 - v15;
        (*(void (__fastcall **)(CryptoBase *, char *))(*(_QWORD *)this + 224LL))(this, v5);
        if ( v16 )
        {
          if ( v22 )
          {
            _mm_lfence();
            memmove_s(v5, v16, &v5[v21], v16);
          }
          *((_DWORD *)v20 + 22) = v16;
          a2 = v20;
        }
        else
        {
          SNIPacketRelease(v20);
          a2 = 0;
          v20 = 0;
        }
        if ( v16 != v21 && !v19 )
          continue;
        if ( !a2 || (*((_BYTE *)this + 96) & 8) == 0 )
        {
          *((_QWORD *)this + 7) = a2;
          v20 = 0;
          goto LABEL_71;
        }
        _mm_lfence();
        v4 = -2146893048;
        if ( (bidGblFlags & 2) != 0 && off_1005E51E0[0] && bidID != -1 )
          ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
            bidID,
            0,
            3100672,
            off_1005E51E0[0],
            0);
        if ( (bidGblFlags & 2) != 0 && off_1005E51E8[0] )
        {
          _mm_lfence();
          SniErrorIdFromStringId(0xC3B4u);
          bidTraceW(0, 3101696, off_1005E51E8[0], *((unsigned int *)this + 6));
        }
        SNISetLastError(*((unsigned int *)this + 6), 2148074248LL, 50100);
        *((_DWORD *)this + 54) = 2;
        *((_DWORD *)this + 55) = 26;
      }
      break;
    }
  }
LABEL_69:
  if ( v20 )
    SNIPacketRelease(v20);
LABEL_71:
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E51F0[0] )
    bidTraceW(0, 3125248, off_1005E51F0[0], v4);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v18);
  return v4;
}

```

## disassembly

```asm
0x100425d10  mov     [rsp-38h+arg_8], rdx
0x100425d15  push    rbp
0x100425d16  push    rbx
0x100425d17  push    rsi
0x100425d18  push    rdi
0x100425d19  push    r12
0x100425d1b  push    r14
0x100425d1d  push    r15
0x100425d1f  mov     rbp, rsp
0x100425d22  sub     rsp, 50h
0x100425d26  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x100425d2e  mov     rbx, rcx
0x100425d31  or      [rbp+var_10], 0FFFFFFFFFFFFFFFFh
0x100425d36  mov     eax, cs:_bidGblFlags
0x100425d3c  mov     ecx, 20004h
0x100425d41  and     eax, ecx
0x100425d43  cmp     eax, ecx
0x100425d45  jnz     short loc_100425D6F
0x100425d47  mov     rax, cs:off_1005E7B18; "<CryptoBase::HandshakeReadToken|API|SNI"...
0x100425d4e  test    rax, rax
0x100425d51  jz      short loc_100425D6B
0x100425d53  mov     r9, [rbp+arg_8]
0x100425d57  mov     r8d, [rbx+2Ch]
0x100425d5b  mov     rdx, cs:off_1005E7B18; "<CryptoBase::HandshakeReadToken|API|SNI"...
0x100425d62  lea     rcx, [rbp+var_10]
0x100425d66  call    _bidScopeEnterW
0x100425d6b  mov     rdx, [rbp+arg_8]
0x100425d6f  xor     r12d, r12d
0x100425d72  cmp     [rbx+38h], r12
0x100425d76  jz      loc_100425E34
0x100425d7c  test    byte ptr cs:_bidGblFlags, 2
0x100425d83  jz      short loc_100425DC3
0x100425d85  mov     rax, cs:off_1005E51B0; "<CryptoBase::HandshakeReadToken|ERR|SNI"...
0x100425d8c  test    rax, rax
0x100425d8f  jz      short loc_100425DC3
0x100425d91  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100425d99  jz      short loc_100425DC3
0x100425d9b  mov     rax, cs:off_1005D39E0
0x100425da2  and     [rsp+50h+var_30], r12
0x100425da7  mov     r9, cs:off_1005E51B0; "<CryptoBase::HandshakeReadToken|ERR|SNI"...
0x100425dae  xor     edx, edx
0x100425db0  mov     r8d, 2CD800h
0x100425db6  mov     rcx, cs:_bidID
0x100425dbd  call    cs:__guard_dispatch_icall_fptr
0x100425dc3  mov     r14d, 80090308h
0x100425dc9  mov     edi, r14d
0x100425dcc  mov     esi, 0C3B4h
0x100425dd1  test    byte ptr cs:_bidGblFlags, 2
0x100425dd8  jz      short loc_100425E0D
0x100425dda  mov     rax, cs:off_1005E51B8; "<CryptoBase::HandshakeReadToken|ERR|SNI"...
0x100425de1  test    rax, rax
0x100425de4  jz      short loc_100425E0D
0x100425de6  mov     ecx, esi; unsigned int
0x100425de8  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100425ded  mov     dword ptr [rsp+50h+var_28], r14d
0x100425df2  mov     dword ptr [rsp+50h+var_30], eax
0x100425df6  mov     r9d, [rbx+18h]
0x100425dfa  mov     r8, cs:off_1005E51B8; "<CryptoBase::HandshakeReadToken|ERR|SNI"...
0x100425e01  mov     edx, 2CE400h
0x100425e06  xor     ecx, ecx
0x100425e08  call    _bidTraceW
0x100425e0d  mov     r8d, esi
0x100425e10  mov     edx, r14d
0x100425e13  mov     ecx, [rbx+18h]
0x100425e16  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100425e1b  mov     dword ptr [rbx+0D8h], 2
0x100425e25  mov     dword ptr [rbx+0DCh], 17h
0x100425e2f  jmp     loc_100426284
0x100425e34  mov     r14d, 80090308h
0x100425e3a  xor     r15d, r15d
0x100425e3d  and     [rbp+arg_18], r15d
0x100425e41  mov     [rbp+arg_0], r15b
0x100425e45  xor     esi, esi
0x100425e47  test    rdx, rdx
0x100425e4a  jz      short loc_100425E5B
0x100425e4c  mov     r15d, [rdx+60h]
0x100425e50  add     r15, [rdx+50h]
0x100425e54  mov     esi, [rdx+58h]
0x100425e57  mov     r12d, [rdx+5Ch]
0x100425e5b  mov     rax, [rbx+0E0h]
0x100425e62  lea     rcx, [rbp+arg_0]
0x100425e66  mov     [rsp+50h+var_28], rcx
0x100425e6b  mov     dword ptr [rsp+50h+var_30], r12d
0x100425e70  lea     r9, [rbp+arg_18]
0x100425e74  lea     r8, [rbp+arg_10]
0x100425e78  mov     edx, esi
0x100425e7a  mov     rcx, r15
0x100425e7d  mov     rax, [rax+48h]
0x100425e81  call    cs:__guard_dispatch_icall_fptr
0x100425e87  mov     edi, eax
0x100425e89  cmp     eax, 80090318h
0x100425e8e  jz      short loc_100425EA2
0x100425e90  cmp     eax, r14d
0x100425e93  jz      loc_1004261BE
0x100425e99  cmp     esi, [rbp+arg_10]
0x100425e9c  jnb     loc_100425F47
0x100425ea2  mov     rcx, [rbx+8]
0x100425ea6  mov     rax, [rbx+20h]
0x100425eaa  mov     rdx, [rbp+arg_8]
0x100425eae  test    byte ptr [rax+0ECh], 1
0x100425eb5  mov     rax, [rcx]
0x100425eb8  jz      short loc_100425EEB
0x100425eba  test    rdx, rdx
0x100425ebd  jz      short loc_100425ED5
0x100425ebf  mov     r8d, r12d
0x100425ec2  sub     r8d, esi
0x100425ec5  or      r9d, 0FFFFFFFFh
0x100425ec9  mov     rax, [rax+10h]
0x100425ecd  call    cs:__guard_dispatch_icall_fptr
0x100425ed3  jmp     short loc_100425EE7
0x100425ed5  or      r8d, 0FFFFFFFFh
0x100425ed9  lea     rdx, [rbp+arg_8]
0x100425edd  mov     rax, [rax+70h]
0x100425ee1  call    cs:__guard_dispatch_icall_fptr
0x100425ee7  mov     edi, eax
0x100425ee9  jmp     short loc_100425F23
0x100425eeb  test    rdx, rdx
0x100425eee  jz      short loc_100425F05
0x100425ef0  mov     r8d, r12d
0x100425ef3  sub     r8d, esi
0x100425ef6  xor     r9d, r9d
0x100425ef9  mov     rax, [rax+18h]
0x100425efd  call    cs:__guard_dispatch_icall_fptr
0x100425f03  jmp     short loc_100425F16
0x100425f05  xor     r8d, r8d
0x100425f08  lea     rdx, [rbp+arg_8]
0x100425f0c  mov     rax, [rax+78h]
0x100425f10  call    cs:__guard_dispatch_icall_fptr
0x100425f16  mov     edi, eax
0x100425f18  cmp     eax, 3E5h
0x100425f1d  jz      loc_100426271
0x100425f23  mov     eax, edi
0x100425f25  test    edi, edi
0x100425f27  jnz     loc_100426254
0x100425f2d  test    byte ptr [rbx+60h], 8
0x100425f31  jnz     short loc_100425F3E
0x100425f33  mov     rax, [rbx+20h]
0x100425f37  lock inc dword ptr [rax+0CCh]
0x100425f3e  mov     rdx, [rbp+arg_8]
0x100425f42  jmp     loc_100425E45
0x100425f47  mov     rax, [rbx]
0x100425f4a  mov     rcx, rbx
0x100425f4d  mov     rax, [rax+0C0h]
0x100425f54  call    cs:__guard_dispatch_icall_fptr
0x100425f5a  add     eax, [rbx+0CCh]
0x100425f60  mov     edx, [rbx+0A8h]
0x100425f66  sub     edx, [rbp+arg_18]
0x100425f69  add     edx, [rbp+arg_10]
0x100425f6c  add     eax, [rbx+0C8h]
0x100425f72  lfence
0x100425f75  cmp     edx, eax
0x100425f77  ja      loc_1004260F2
0x100425f7d  mov     eax, [rbp+arg_10]
0x100425f80  sub     eax, [rbp+arg_18]
0x100425f83  mov     edx, eax; DestinationSize
0x100425f85  mov     r8d, [rbp+arg_18]
0x100425f89  add     r8, r15; Source
0x100425f8c  mov     ecx, [rbx+0A8h]
0x100425f92  add     rcx, [rbx+98h]; Destination
0x100425f99  mov     r9d, eax; SourceSize
0x100425f9c  call    cs:__imp_memcpy_s
0x100425fa2  mov     r8d, [rbp+arg_10]
0x100425fa6  mov     eax, r8d
0x100425fa9  sub     eax, [rbp+arg_18]
0x100425fac  add     [rbx+0A8h], eax
0x100425fb2  sub     esi, r8d
0x100425fb5  mov     rax, [rbx]
0x100425fb8  mov     rdx, r15
0x100425fbb  mov     rcx, rbx
0x100425fbe  mov     rax, [rax+0E0h]
0x100425fc5  call    cs:__guard_dispatch_icall_fptr
0x100425fcb  test    esi, esi
0x100425fcd  jz      short loc_100425FFA
0x100425fcf  cmp     [rbp+arg_18], 0
0x100425fd3  jbe     short loc_100425FED
0x100425fd5  lfence
0x100425fd8  mov     edx, esi; DestinationSize
0x100425fda  mov     r8d, [rbp+arg_10]
0x100425fde  add     r8, r15; Source
0x100425fe1  mov     r9d, esi; SourceSize
0x100425fe4  mov     rcx, r15; Destination
0x100425fe7  call    cs:__imp_memmove_s
0x100425fed  mov     rax, [rbp+arg_8]
0x100425ff1  mov     [rax+58h], esi
0x100425ff4  mov     rdx, [rbp+arg_8]
0x100425ff8  jmp     short loc_100426009
0x100425ffa  mov     rcx, [rbp+arg_8]; this
0x100425ffe  call    SNIPacketRelease
0x100426003  xor     edx, edx
0x100426005  mov     [rbp+arg_8], rdx
0x100426009  cmp     esi, [rbp+arg_10]
0x10042600c  jz      short loc_100426018
0x10042600e  cmp     [rbp+arg_0], 0
0x100426012  jz      loc_100425E3A
0x100426018  test    rdx, rdx
0x10042601b  jz      loc_1004260E4
0x100426021  test    byte ptr [rbx+60h], 8
0x100426025  jz      loc_1004260E4
0x10042602b  lfence
0x10042602e  mov     edi, r14d
0x100426031  test    byte ptr cs:_bidGblFlags, 2
0x100426038  jz      short loc_100426079
0x10042603a  mov     rax, cs:off_1005E51E0; "<CryptoBase::HandshakeReadToken|ERR|SNI"...
0x100426041  test    rax, rax
0x100426044  jz      short loc_100426079
0x100426046  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10042604e  jz      short loc_100426079
0x100426050  mov     rax, cs:off_1005D39E0
0x100426057  and     [rsp+50h+var_30], 0
0x10042605d  mov     r9, cs:off_1005E51E0; "<CryptoBase::HandshakeReadToken|ERR|SNI"...
0x100426064  xor     edx, edx
0x100426066  mov     r8d, 2F5000h
0x10042606c  mov     rcx, cs:_bidID
0x100426073  call    cs:__guard_dispatch_icall_fptr
0x100426079  mov     esi, 0C3B4h
0x10042607e  test    byte ptr cs:_bidGblFlags, 2
0x100426085  jz      short loc_1004260BD
0x100426087  mov     rax, cs:off_1005E51E8; "<CryptoBase::HandshakeReadToken|ERR|SNI"...
0x10042608e  test    rax, rax
0x100426091  jz      short loc_1004260BD
0x100426093  lfence
0x100426096  mov     ecx, esi; unsigned int
0x100426098  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10042609d  mov     dword ptr [rsp+50h+var_28], r14d
0x1004260a2  mov     dword ptr [rsp+50h+var_30], eax
0x1004260a6  mov     r9d, [rbx+18h]
0x1004260aa  mov     r8, cs:off_1005E51E8; "<CryptoBase::HandshakeReadToken|ERR|SNI"...
0x1004260b1  mov     edx, 2F5400h
0x1004260b6  xor     ecx, ecx
0x1004260b8  call    _bidTraceW
0x1004260bd  mov     r8d, esi
0x1004260c0  mov     edx, r14d
0x1004260c3  mov     ecx, [rbx+18h]
0x1004260c6  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1004260cb  mov     dword ptr [rbx+0D8h], 2
0x1004260d5  mov     dword ptr [rbx+0DCh], 1Ah
0x1004260df  jmp     loc_100426284
0x1004260e4  mov     [rbx+38h], rdx
0x1004260e8  and     [rbp+arg_8], 0
0x1004260ed  jmp     loc_100426292
0x1004260f2  mov     edi, r14d
0x1004260f5  test    byte ptr cs:_bidGblFlags, 2
0x1004260fc  jz      short loc_100426156
0x1004260fe  mov     rax, cs:off_1005E51D0; "<CryptoBase::HandshakeReadToken|ERR|SNI"...
0x100426105  test    rax, rax
0x100426108  jz      short loc_100426156
0x10042610a  mov     rax, [rbx]
0x10042610d  mov     rcx, rbx
0x100426110  mov     rax, [rax+0C0h]
0x100426117  call    cs:__guard_dispatch_icall_fptr
0x10042611d  mov     ecx, [rbx+0CCh]
0x100426123  mov     [rsp+50h+var_18], ecx
0x100426127  mov     ecx, [rbx+0C8h]
0x10042612d  mov     [rsp+50h+var_20], ecx
0x100426131  mov     dword ptr [rsp+50h+var_28], eax
0x100426135  mov     eax, [rbx+0A8h]
0x10042613b  mov     dword ptr [rsp+50h+var_30], eax
0x10042613f  mov     r9d, [rbp+arg_10]
0x100426143  mov     r8, cs:off_1005E51D0; "<CryptoBase::HandshakeReadToken|ERR|SNI"...
0x10042614a  mov     edx, 2E9C00h
0x10042614f  xor     ecx, ecx
0x100426151  call    _bidTraceW
0x100426156  mov     esi, 0C3B4h
0x10042615b  test    byte ptr cs:_bidGblFlags, 2
0x100426162  jz      short loc_100426197
0x100426164  mov     rax, cs:off_1005E51D8; "<CryptoBase::HandshakeReadToken|ERR|SNI"...
0x10042616b  test    rax, rax
0x10042616e  jz      short loc_100426197
0x100426170  mov     ecx, esi; unsigned int
0x100426172  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100426177  mov     dword ptr [rsp+50h+var_28], r14d
0x10042617c  mov     dword ptr [rsp+50h+var_30], eax
0x100426180  mov     r9d, [rbx+18h]
0x100426184  mov     r8, cs:off_1005E51D8; "<CryptoBase::HandshakeReadToken|ERR|SNI"...
0x10042618b  mov     edx, 2EA000h
0x100426190  xor     ecx, ecx
0x100426192  call    _bidTraceW
0x100426197  mov     r8d, esi
0x10042619a  mov     edx, r14d
0x10042619d  mov     ecx, [rbx+18h]
0x1004261a0  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1004261a5  mov     dword ptr [rbx+0D8h], 2
0x1004261af  mov     dword ptr [rbx+0DCh], 19h
0x1004261b9  jmp     loc_100426284
0x1004261be  test    byte ptr cs:_bidGblFlags, 2
0x1004261c5  jz      short loc_1004261EF
0x1004261c7  mov     rax, cs:off_1005E51C0; "<CryptoBase::HandshakeReadToken|ERR|SNI"...
0x1004261ce  test    rax, rax
0x1004261d1  jz      short loc_1004261EF
0x1004261d3  mov     dword ptr [rsp+50h+var_30], r12d
0x1004261d8  mov     r9d, [rbp+arg_10]
0x1004261dc  mov     r8, cs:off_1005E51C0; "<CryptoBase::HandshakeReadToken|ERR|SNI"...
0x1004261e3  mov     edx, 2D8C00h
0x1004261e8  xor     ecx, ecx
0x1004261ea  call    _bidTraceW
0x1004261ef  mov     esi, 0C3B4h
0x1004261f4  test    byte ptr cs:_bidGblFlags, 2
0x1004261fb  jz      short loc_100426230
0x1004261fd  mov     rax, cs:off_1005E51C8; "<CryptoBase::HandshakeReadToken|ERR|SNI"...
0x100426204  test    rax, rax
  ... truncated ...
```
