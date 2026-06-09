# CCAPIStm::StreamOutput(uchar *,ulong,int)

- ea: `0x18005bb2c`
- end: `0x18005be38`
- name: `?StreamOutput@CCAPIStm@@AEAAHPEAEKH@Z`
- size: `780`
- prototype: `__int64 __fastcall(CCAPIStm *__hidden this, unsigned __int8 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18005a2b0`

## callees

- `0x18000d50c`
- `0x180016c88`
- `0x180016f2c`
- `0x18001e7e4`
- `0x18001f324`
- `0x1800299d0`
- `0x18005afac`
- `0x18005ba9c`
- `0x18005bb2c`
- `0x18005f2b4`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!HrStreamSeekSet` at `0x18005bbc0`
- `MSOERT2!HrStreamSeekSet` at `0x18005bd35`
- `MSOERT2!HrStreamSeekSet` at `0x18005bd58`
- `MSOERT2!HrStreamSeekSet` at `0x18005bbc0`
- `MSOERT2!HrStreamSeekSet` at `0x18005bd35`
- `MSOERT2!HrStreamSeekSet` at `0x18005bd58`
- `MSOERT2!HrGetStreamSize` at `0x18005bbb0`
- `MSOERT2!HrGetStreamSize` at `0x18005bbb0`
- `MSOERT2!HrGetStreamPos` at `0x18005bb9b`
- `MSOERT2!HrGetStreamPos` at `0x18005bd28`
- `MSOERT2!HrGetStreamPos` at `0x18005bb9b`
- `MSOERT2!HrGetStreamPos` at `0x18005bd28`
- `MSOERT2!PVGetMsgParam` at `0x18005bbe3`
- `MSOERT2!PVGetMsgParam` at `0x18005bbe3`
- `KERNEL32!lstrcmpA` at `0x18005bbff`
- `KERNEL32!lstrcmpA` at `0x18005bbff`

## pseudocode

```c
_BOOL8 __fastcall CCAPIStm::StreamOutput(CCAPIStm *this, unsigned __int8 *a2, unsigned int a3, int a4)
{
  __int64 v8; // rcx
  const CHAR *v10; // r14
  _DWORD *v11; // rsi
  __int64 v12; // rcx
  const CHAR *v13; // rax
  __int64 v14; // r8
  int v15; // ebx
  CMimePropertyContainer *v16; // rax
  CMimePropertyContainer *v17; // rax
  struct CMimePropertyContainer *v18; // rsi
  int v19; // ebx
  int v20; // ebx
  CInternetConverter *v21; // rcx
  int v22; // eax
  __int64 v23; // r8
  __int64 v24; // r9
  CInternetConverter *v25; // rcx
  __int64 v26; // rcx
  int v27; // eax
  int v28; // ebx
  struct tagBLOB v29; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v30; // [rsp+70h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 4) == 36 )
    return 1;
  v8 = *((_QWORD *)this + 6);
  if ( !v8 )
  {
    if ( a4 )
      *((_DWORD *)this + 4) = 35;
    return 1;
  }
  v10 = 0;
  if ( *((_DWORD *)this + 4) == 32 )
  {
    v11 = (_DWORD *)((char *)this + 80);
    if ( (int)HrGetStreamPos(v8, (char *)this + 80) < 0
      || (int)HrGetStreamSize(*((_QWORD *)this + 6), (char *)this + 84) < 0 )
    {
      *v11 = 0;
      *((_DWORD *)this + 21) = 0;
    }
    else
    {
      HrStreamSeekSet(*((_QWORD *)this + 6), (unsigned int)*v11);
    }
    v12 = *((_QWORD *)this + 3);
    *((_DWORD *)this + 4) = 33;
    v13 = (const CHAR *)PVGetMsgParam(v12, 4, 0);
    v10 = v13;
    if ( v13 )
    {
      if ( lstrcmpA("1.2.840.113549.1.7.1", v13) )
      {
        if ( (*(int (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 6) + 32LL))(
               *((_QWORD *)this + 6),
               "Content-Type: oid/",
               18) < 0 )
          return 0;
        v14 = -1;
        do
          ++v14;
        while ( v10[v14] );
        if ( (*(int (__fastcall **)(_QWORD, const CHAR *, __int64, _QWORD))(**((_QWORD **)this + 6) + 32LL))(
               *((_QWORD *)this + 6),
               v10,
               v14,
               0) < 0
          || (*(int (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 6) + 32LL))(
               *((_QWORD *)this + 6),
               "\nContent-Transfer-Encoding: binary\n\n",
               36) < 0 )
        {
          return 0;
        }
        *((_DWORD *)this + 4) = 34;
      }
    }
  }
  if ( *((_DWORD *)this + 4) == 33 )
  {
    v15 = CCAPIStm::SniffForEndOfHeader(this, a2, a3);
    if ( v15 != -1 )
    {
      v16 = (CMimePropertyContainer *)operator new(0x5A0u);
      if ( v16 )
      {
        v17 = CMimePropertyContainer::CMimePropertyContainer(v16);
        v18 = v17;
        if ( v17 )
        {
          if ( (*(int (__fastcall **)(CMimePropertyContainer *))(*(_QWORD *)v17 + 64LL))(v17) >= 0 )
          {
            v30 = 0;
            v19 = a3 - v15 + 1;
            if ( (*(int (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, _QWORD))(**((_QWORD **)this + 6) + 32LL))(
                   *((_QWORD *)this + 6),
                   a2,
                   (unsigned int)v19,
                   0) >= 0 )
            {
              a3 -= v19;
              a2 += v19;
              HrGetStreamPos(*((_QWORD *)this + 6), &v30);
              HrStreamSeekSet(*((_QWORD *)this + 6), *((unsigned int *)this + 20));
              v20 = (*(__int64 (__fastcall **)(struct CMimePropertyContainer *, _QWORD))(*(_QWORD *)v18 + 40LL))(
                      v18,
                      *((_QWORD *)this + 6));
              HrStreamSeekSet(*((_QWORD *)this + 6), v30);
              if ( v20 >= 0 )
              {
                if ( (unsigned int)IsOpaqueSecureContentType(v18) )
                  CCAPIStm::HandleNesting(this, v18);
                *((_DWORD *)this + 4) = 34;
              }
            }
          }
          (*(void (__fastcall **)(struct CMimePropertyContainer *))(*(_QWORD *)v18 + 16LL))(v18);
        }
      }
    }
  }
  if ( a4 )
    *((_DWORD *)this + 4) = 35;
  v21 = (CInternetConverter *)*((_QWORD *)this + 11);
  if ( !v21 )
  {
    v26 = *((_QWORD *)this + 6);
LABEL_41:
    v27 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, _QWORD, _QWORD))(*(_QWORD *)v26 + 32LL))(
            v26,
            a2,
            a3,
            0);
    goto LABEL_42;
  }
  *(&v29.cbSize + 1) = 0;
  v29.pBlobData = a2;
  v29.cbSize = a3;
  v22 = CInternetConverter::HrFillAppend(v21, &v29);
  if ( v22 >= 0 )
  {
    v25 = (CInternetConverter *)*((_QWORD *)this + 11);
    if ( (*((_DWORD *)this + 16) & 0x10000) != 0 )
      v22 = CInternetConverter::HrInternetDecode(v25, a4, v23, v24);
    else
      v22 = CInternetConverter::HrInternetEncode(v25, a4);
  }
  v26 = *((_QWORD *)this + 6);
  if ( v22 < 0 )
    goto LABEL_41;
  v27 = CInternetConverter::HrWriteConverted(*((CInternetConverter **)this + 11), *((struct IStream **)this + 6));
LABEL_42:
  v28 = v27;
  ((void (__fastcall *)(LPMALLOC, const CHAR *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v10);
  return v28 >= 0;
}

```

## disassembly

```asm
0x18005bb2c  mov     [rsp+arg_8], rbx
0x18005bb31  mov     [rsp+arg_10], rbp
0x18005bb36  push    rsi
0x18005bb37  push    rdi
0x18005bb38  push    r12
0x18005bb3a  push    r14
0x18005bb3c  push    r15
0x18005bb3e  sub     rsp, 40h
0x18005bb42  cmp     dword ptr [rcx+10h], 24h ; '$'
0x18005bb46  mov     ebp, r9d
0x18005bb49  mov     r15d, r8d
0x18005bb4c  mov     r12, rdx
0x18005bb4f  mov     rdi, rcx
0x18005bb52  jz      short loc_18005BB69
0x18005bb54  mov     rcx, [rcx+30h]
0x18005bb58  test    rcx, rcx
0x18005bb5b  jnz     short loc_18005BB87
0x18005bb5d  test    r9d, r9d
0x18005bb60  jz      short loc_18005BB69
0x18005bb62  mov     dword ptr [rdi+10h], 23h ; '#'
0x18005bb69  mov     eax, 1
0x18005bb6e  lea     r11, [rsp+68h+var_28]
0x18005bb73  mov     rbx, [r11+38h]
0x18005bb77  mov     rbp, [r11+40h]
0x18005bb7b  mov     rsp, r11
0x18005bb7e  pop     r15
0x18005bb80  pop     r14
0x18005bb82  pop     r12
0x18005bb84  pop     rdi
0x18005bb85  pop     rsi
0x18005bb86  retn
0x18005bb87  xor     r14d, r14d
0x18005bb8a  cmp     dword ptr [rdi+10h], 20h ; ' '
0x18005bb8e  jnz     loc_18005BC88
0x18005bb94  lea     rsi, [rdi+50h]
0x18005bb98  mov     rdx, rsi
0x18005bb9b  call    cs:__imp_HrGetStreamPos
0x18005bba1  lea     rbx, [rdi+54h]
0x18005bba5  test    eax, eax
0x18005bba7  js      short loc_18005BBC8
0x18005bba9  mov     rcx, [rdi+30h]
0x18005bbad  mov     rdx, rbx
0x18005bbb0  call    cs:__imp_HrGetStreamSize
0x18005bbb6  test    eax, eax
0x18005bbb8  js      short loc_18005BBC8
0x18005bbba  mov     edx, [rsi]
0x18005bbbc  mov     rcx, [rdi+30h]
0x18005bbc0  call    cs:__imp_HrStreamSeekSet
0x18005bbc6  jmp     short loc_18005BBCE
0x18005bbc8  mov     [rsi], r14d
0x18005bbcb  mov     [rbx], r14d
0x18005bbce  mov     rcx, [rdi+18h]
0x18005bbd2  xor     r9d, r9d
0x18005bbd5  xor     r8d, r8d
0x18005bbd8  mov     dword ptr [rdi+10h], 21h ; '!'
0x18005bbdf  lea     edx, [r9+4]
0x18005bbe3  call    cs:__imp_PVGetMsgParam
0x18005bbe9  mov     r14, rax
0x18005bbec  test    rax, rax
0x18005bbef  jz      loc_18005BC88
0x18005bbf5  mov     rdx, rax; lpString2
0x18005bbf8  lea     rcx, String1; "1.2.840.113549.1.7.1"
0x18005bbff  call    cs:__imp_lstrcmpA
0x18005bc05  test    eax, eax
0x18005bc07  jz      short loc_18005BC88
0x18005bc09  mov     rcx, [rdi+30h]
0x18005bc0d  xor     r9d, r9d
0x18005bc10  mov     rdx, [rcx]
0x18005bc13  lea     r8d, [r9+12h]
0x18005bc17  mov     rax, [rdx+20h]
0x18005bc1b  lea     rdx, aContentTypeOid; "Content-Type: oid/"
0x18005bc22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc27  test    eax, eax
0x18005bc29  js      loc_18005BDD9
0x18005bc2f  mov     rcx, [rdi+30h]
0x18005bc33  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005bc37  mov     rax, [rcx]
0x18005bc3a  inc     r8
0x18005bc3d  cmp     byte ptr [r14+r8], 0
0x18005bc42  jnz     short loc_18005BC3A
0x18005bc44  mov     rax, [rax+20h]
0x18005bc48  xor     r9d, r9d
0x18005bc4b  mov     rdx, r14
0x18005bc4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc53  test    eax, eax
0x18005bc55  js      loc_18005BDD9
0x18005bc5b  mov     rcx, [rdi+30h]
0x18005bc5f  lea     rdx, aContentTransfe; "\nContent-Transfer-Encoding: binary\n\n"
0x18005bc66  xor     r9d, r9d
0x18005bc69  mov     rax, [rcx]
0x18005bc6c  lea     r8d, [r9+24h]
0x18005bc70  mov     rax, [rax+20h]
0x18005bc74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc79  test    eax, eax
0x18005bc7b  js      loc_18005BDD9
0x18005bc81  mov     dword ptr [rdi+10h], 22h ; '"'
0x18005bc88  cmp     dword ptr [rdi+10h], 21h ; '!'
0x18005bc8c  jnz     loc_18005BD8F
0x18005bc92  mov     r8d, r15d; unsigned int
0x18005bc95  mov     rdx, r12; unsigned __int8 *
0x18005bc98  mov     rcx, rdi; this
0x18005bc9b  call    ?SniffForEndOfHeader@CCAPIStm@@IEAAHPEBEK@Z; CCAPIStm::SniffForEndOfHeader(uchar const *,ulong)
0x18005bca0  mov     ebx, eax
0x18005bca2  cmp     eax, 0FFFFFFFFh
0x18005bca5  jz      loc_18005BD8F
0x18005bcab  mov     ecx, 5A0h; Size
0x18005bcb0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005bcb5  test    rax, rax
0x18005bcb8  jz      loc_18005BD8F
0x18005bcbe  mov     rcx, rax; this
0x18005bcc1  call    ??0CMimePropertyContainer@@QEAA@XZ; CMimePropertyContainer::CMimePropertyContainer(void)
0x18005bcc6  mov     rsi, rax
0x18005bcc9  test    rax, rax
0x18005bccc  jz      loc_18005BD8F
0x18005bcd2  mov     rcx, [rax]
0x18005bcd5  mov     rax, [rcx+40h]
0x18005bcd9  mov     rcx, rsi
0x18005bcdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bce1  test    eax, eax
0x18005bce3  js      loc_18005BD80
0x18005bce9  mov     ecx, r15d
0x18005bcec  mov     [rsp+68h+arg_0], 0
0x18005bcf4  sub     ecx, ebx
0x18005bcf6  xor     r9d, r9d
0x18005bcf9  mov     rdx, r12
0x18005bcfc  lea     ebx, [rcx+1]
0x18005bcff  mov     rcx, [rdi+30h]
0x18005bd03  mov     r8d, ebx
0x18005bd06  mov     rax, [rcx]
0x18005bd09  mov     rax, [rax+20h]
0x18005bd0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd12  test    eax, eax
0x18005bd14  js      short loc_18005BD80
0x18005bd16  mov     rcx, [rdi+30h]
0x18005bd1a  lea     rdx, [rsp+68h+arg_0]
0x18005bd1f  movsxd  rax, ebx
0x18005bd22  sub     r15d, ebx
0x18005bd25  add     r12, rax
0x18005bd28  call    cs:__imp_HrGetStreamPos
0x18005bd2e  mov     edx, [rdi+50h]
0x18005bd31  mov     rcx, [rdi+30h]
0x18005bd35  call    cs:__imp_HrStreamSeekSet
0x18005bd3b  mov     rax, [rsi]
0x18005bd3e  mov     rcx, rsi
0x18005bd41  mov     rdx, [rdi+30h]
0x18005bd45  mov     rax, [rax+28h]
0x18005bd49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd4e  mov     edx, [rsp+68h+arg_0]
0x18005bd52  mov     ebx, eax
0x18005bd54  mov     rcx, [rdi+30h]
0x18005bd58  call    cs:__imp_HrStreamSeekSet
0x18005bd5e  test    ebx, ebx
0x18005bd60  js      short loc_18005BD80
0x18005bd62  mov     rcx, rsi; struct IMimePropertySet *
0x18005bd65  call    ?IsOpaqueSecureContentType@@YAHPEAUIMimePropertySet@@@Z; IsOpaqueSecureContentType(IMimePropertySet *)
0x18005bd6a  test    eax, eax
0x18005bd6c  jz      short loc_18005BD79
0x18005bd6e  mov     rdx, rsi; struct CMimePropertyContainer *
0x18005bd71  mov     rcx, rdi; this
0x18005bd74  call    ?HandleNesting@CCAPIStm@@AEAAJPEAVCMimePropertyContainer@@@Z; CCAPIStm::HandleNesting(CMimePropertyContainer *)
0x18005bd79  mov     dword ptr [rdi+10h], 22h ; '"'
0x18005bd80  mov     rax, [rsi]
0x18005bd83  mov     rcx, rsi
0x18005bd86  mov     rax, [rax+10h]
0x18005bd8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd8f  test    ebp, ebp
0x18005bd91  jz      short loc_18005BD9A
0x18005bd93  mov     dword ptr [rdi+10h], 23h ; '#'
0x18005bd9a  mov     rcx, [rdi+58h]; this
0x18005bd9e  test    rcx, rcx
0x18005bda1  jz      short loc_18005BDFB
0x18005bda3  lea     rdx, [rsp+68h+var_38]; struct tagBLOB *
0x18005bda8  mov     dword ptr [rsp+68h+var_38+4], 0
0x18005bdb0  mov     [rsp+68h+var_38.pBlobData], r12
0x18005bdb5  mov     [rsp+68h+var_38.cbSize], r15d
0x18005bdba  call    ?HrFillAppend@CInternetConverter@@QEAAJPEAUtagBLOB@@@Z; CInternetConverter::HrFillAppend(tagBLOB *)
0x18005bdbf  test    eax, eax
0x18005bdc1  js      short loc_18005BDE5
0x18005bdc3  test    dword ptr [rdi+40h], 10000h
0x18005bdca  mov     edx, ebp; int
0x18005bdcc  mov     rcx, [rdi+58h]; this
0x18005bdd0  jz      short loc_18005BDE0
0x18005bdd2  call    ?HrInternetDecode@CInternetConverter@@QEAAJH@Z; CInternetConverter::HrInternetDecode(int)
0x18005bdd7  jmp     short loc_18005BDE5
0x18005bdd9  xor     eax, eax
0x18005bddb  jmp     loc_18005BB6E
0x18005bde0  call    ?HrInternetEncode@CInternetConverter@@QEAAJH@Z; CInternetConverter::HrInternetEncode(int)
0x18005bde5  mov     rcx, [rdi+30h]
0x18005bde9  test    eax, eax
0x18005bdeb  js      short loc_18005BDFF
0x18005bded  mov     rdx, rcx; struct IStream *
0x18005bdf0  mov     rcx, [rdi+58h]; this
0x18005bdf4  call    ?HrWriteConverted@CInternetConverter@@QEAAJPEAUIStream@@@Z; CInternetConverter::HrWriteConverted(IStream *)
0x18005bdf9  jmp     short loc_18005BE14
0x18005bdfb  mov     rcx, [rdi+30h]
0x18005bdff  mov     rax, [rcx]
0x18005be02  xor     r9d, r9d
0x18005be05  mov     r8d, r15d
0x18005be08  mov     rdx, r12
0x18005be0b  mov     rax, [rax+20h]
0x18005be0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be14  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18005be1b  mov     ebx, eax
0x18005be1d  mov     rdx, r14
0x18005be20  mov     rax, [rcx]
0x18005be23  mov     rax, [rax+28h]
0x18005be27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be2c  not     ebx
0x18005be2e  shr     ebx, 1Fh
0x18005be31  mov     eax, ebx
0x18005be33  jmp     loc_18005BB6E
```
