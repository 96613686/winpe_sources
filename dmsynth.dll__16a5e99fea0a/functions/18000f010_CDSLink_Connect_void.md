# CDSLink::Connect(void)

- ea: `0x18000f010`
- end: `0x18000f63d`
- name: `?Connect@CDSLink@@AEAAJXZ`
- size: `1581`
- prototype: `__int64 __fastcall(CDSLink *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000ef90`

## callees

- `0x1800014f0`
- `0x180001d9a`
- `0x18000f010`
- `0x18000fc80`
- `0x180011cc0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f0ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f444`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f0ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f444`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f531`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f541`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f5cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f531`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f541`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f5cd`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000f46a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000f46a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000f49a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000f49a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000f4b4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000f4b4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000f5ee`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000f5ee`

## pseudocode

```c
__int64 __fastcall CDSLink::Connect(CDSLink *this)
{
  char *v3; // rsi
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int16 v8; // ax
  int v9; // edx
  unsigned __int16 v10; // cx
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  _QWORD *v14; // r14
  int v15; // esi
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  const char *v20; // rcx
  unsigned int v21; // edi
  int RegValueDword; // eax
  __int16 v23; // cx
  __int64 v24; // r8
  int v25; // edi
  unsigned int v26; // edx
  __int64 v27; // rcx
  __int64 v28; // r8
  int v29; // edx
  HANDLE Thread; // rax
  _QWORD **v31; // r8
  _QWORD *v32; // rdx
  char *v33; // rcx
  char *v34; // rax
  _QWORD *v35; // rcx
  _QWORD *v36; // r9
  __int64 v37; // rcx
  unsigned __int16 i; // di
  size_t Size; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v40; // [rsp+58h] [rbp-A8h] BYREF
  void *v41; // [rsp+60h] [rbp-A0h] BYREF
  void *v42; // [rsp+68h] [rbp-98h] BYREF
  int v43; // [rsp+70h] [rbp-90h] BYREF
  int v44; // [rsp+74h] [rbp-8Ch]
  __int128 v45; // [rsp+78h] [rbp-88h]
  __int128 v46; // [rsp+88h] [rbp-78h]
  _BYTE v47[20]; // [rsp+98h] [rbp-68h] BYREF
  int v48; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v49; // [rsp+B4h] [rbp-4Ch]
  __int128 v50; // [rsp+C4h] [rbp-3Ch]
  __int128 v51; // [rsp+D4h] [rbp-2Ch]
  __int128 v52; // [rsp+E4h] [rbp-1Ch]
  _BYTE v53[28]; // [rsp+F4h] [rbp-Ch] BYREF

  if ( *((_QWORD *)this + 3) )
  {
    if ( !*((_QWORD *)this + 13) )
      return 2289570105LL;
    v3 = (char *)this + 84;
    if ( (unsigned int)CDSLink::IsValidFormat(this, (const struct tWAVEFORMATEX *)((char *)this + 84)) )
    {
      if ( !*((_QWORD *)this + 7) )
        return 2289570160LL;
      if ( *((_DWORD *)this + 56) )
        return 2289570098LL;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
      v4 = *((_QWORD *)this + 16);
      if ( v4 )
      {
        *((_QWORD *)this + 15) = v4;
        v14 = (_QWORD *)((char *)this + 120);
        v15 = -2147467259;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
        goto LABEL_29;
      }
      v5 = *((_QWORD *)this + 13);
      v43 = 40;
      v44 = 1;
      v45 = 0;
      v46 = 0;
      if ( (*(int (__fastcall **)(__int64, int *, char *, _QWORD))(*(_QWORD *)v5 + 24LL))(
             v5,
             &v43,
             (char *)this + 112,
             0) < 0
        || (v6 = *((_QWORD *)this + 14),
            memset(v47, 0, 18),
            (*(int (__fastcall **)(__int64, _BYTE *, __int64, _QWORD))(*(_QWORD *)v6 + 40LL))(v6, v47, 18, 0) < 0) )
      {
        v15 = -2147418113;
        v14 = (_QWORD *)((char *)this + 120);
        goto LABEL_29;
      }
      v7 = 0;
      v8 = *(_WORD *)&v47[2];
      if ( *(_WORD *)&v47[2] < *((_WORD *)this + 43) )
      {
        v8 = *((_WORD *)this + 43);
        *(_WORD *)&v47[2] = v8;
        v7 = 1;
      }
      v9 = *(_DWORD *)&v47[4];
      if ( *(_DWORD *)&v47[4] < *((_DWORD *)this + 22) )
      {
        v9 = *((_DWORD *)this + 22);
        *(_DWORD *)&v47[4] = v9;
        v7 = 1;
      }
      v10 = *(_WORD *)&v47[14];
      if ( *(_WORD *)&v47[14] >= *((_WORD *)this + 49) )
      {
        if ( !(_DWORD)v7 )
        {
LABEL_22:
          v14 = (_QWORD *)((char *)this + 120);
          v16 = *((_QWORD *)this + 13);
          *(_QWORD *)&v45 = (unsigned int)(2 * *((_DWORD *)this + 23));
          v46 = 0;
          v43 = 40;
          v44 = 98304;
          *((_QWORD *)&v45 + 1) = v3;
          if ( (*(int (__fastcall **)(__int64, int *, char *, _QWORD))(*(_QWORD *)v16 + 24LL))(
                 v16,
                 &v43,
                 (char *)this + 120,
                 0) < 0 )
          {
            v17 = *((_QWORD *)this + 14);
            *v14 = 0;
            if ( v17 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
              *((_QWORD *)this + 14) = 0;
            }
            v15 = -2147418113;
          }
          else
          {
            v15 = 0;
          }
LABEL_29:
          v18 = *v14;
          if ( *v14 )
          {
            *(_DWORD *)v47 = 20;
            *(_OWORD *)&v47[4] = 0;
            if ( (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v18 + 24LL))(v18, v47) >= 0 )
            {
              v19 = *((_QWORD *)this + 13);
              v48 = 96;
              memset(v53, 0, sizeof(v53));
              v49 = 0;
              v50 = 0;
              v51 = 0;
              v52 = 0;
              if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v19 + 32LL))(v19, &v48) >= 0 )
              {
                v21 = 240;
                if ( (v49 & 0x20) == 0 )
                  v21 = 80;
                v40 = v21;
                RegValueDword = GetRegValueDword(v20, "DSLMinLatency", &v40);
                v23 = *((_WORD *)this + 43);
                v24 = *(unsigned int *)&v47[8];
                if ( RegValueDword )
                  v21 = v40;
                v25 = *((_DWORD *)this + 23) * v21;
                *((_DWORD *)this + 53) = *(_DWORD *)&v47[8];
                *((_DWORD *)this + 52) = 0;
                *((_DWORD *)this + 48) = 0;
                *((_QWORD *)this + 23) = 0;
                v42 = 0;
                v41 = 0;
                v26 = ((v25 + 500) / 0x3E8u) >> v23 << v23;
                v27 = *v14;
                *((_DWORD *)this + 54) = v26;
                Size = 0;
                if ( (*(int (__fastcall **)(__int64, _QWORD, __int64, void **, size_t *, void **, char *, _DWORD))(*(_QWORD *)v27 + 88LL))(
                       v27,
                       0,
                       v24,
                       &v42,
                       &Size,
                       &v41,
                       (char *)&Size + 4,
                       0) >= 0 )
                {
                  v28 = (unsigned int)Size;
                  if ( (_DWORD)Size )
                  {
                    memset_0(v42, 0, (unsigned int)Size);
                    v28 = (unsigned int)Size;
                  }
                  v29 = HIDWORD(Size);
                  if ( HIDWORD(Size) )
                  {
                    memset_0(v41, 0, HIDWORD(Size));
                    v28 = (unsigned int)Size;
                    v29 = HIDWORD(Size);
                  }
                  (*(void (__fastcall **)(_QWORD, void *, __int64, void *, int))(*(_QWORD *)*v14 + 152LL))(
                    *v14,
                    v42,
                    v28,
                    v41,
                    v29);
                  if ( (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)*v14 + 96LL))(*v14, 0, 0, 1) >= 0 )
                  {
                    EnterCriticalSection(&CriticalSection);
                    if ( !*((_DWORD *)this + 56) )
                    {
                      if ( !dword_18001E610 )
                      {
                        hEvent = CreateEventA(0, 0, 0, 0);
                        Thread = CreateThread(0, 0, SynthThread, &g_DSLinkList, 0, &ThreadId);
                        hHandle = Thread;
                        if ( Thread )
                          SetThreadPriority(Thread, 15);
                      }
                      v31 = (_QWORD **)g_DSLinkList;
                      v32 = (_QWORD *)((char *)this + 16);
                      v33 = (char *)this + 16;
                      v34 = (char *)g_DSLinkList;
                      if ( !this )
                        v33 = 0;
                      if ( g_DSLinkList )
                      {
                        while ( v34 != v33 )
                        {
                          v34 = *(char **)v34;
                          if ( !v34 )
                            goto LABEL_51;
                        }
                      }
                      else
                      {
LABEL_51:
                        ++dword_18001E610;
                        *v32 = 0;
                        if ( v31 )
                        {
                          v35 = *v31;
                          if ( *v31 )
                          {
                            do
                            {
                              v36 = v35;
                              v35 = (_QWORD *)*v35;
                            }
                            while ( v35 );
                          }
                          else
                          {
                            v36 = v31;
                          }
                          *v36 = v32;
                          v32 = v31;
                        }
                        g_DSLinkList = (__int64)v32;
                      }
                      *((_DWORD *)this + 56) = 1;
                    }
                    LeaveCriticalSection(&CriticalSection);
                    v15 = 0;
                    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
                    goto LABEL_68;
                  }
                }
              }
            }
            v15 = -2147418113;
          }
          else if ( v15 >= 0 )
          {
            goto LABEL_67;
          }
          if ( *v14 )
          {
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 144LL))(*v14);
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 16LL))(*v14);
            *v14 = 0;
          }
          v37 = *((_QWORD *)this + 14);
          if ( v37 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
            *((_QWORD *)this + 14) = 0;
          }
          *((_DWORD *)this + 10) = 1;
          *((_QWORD *)this + 23) = 0;
          *((_DWORD *)this + 48) = 0;
          *((_QWORD *)this + 25) = 0;
          *((_QWORD *)this + 26) = 0;
          *((_DWORD *)this + 54) = 1000;
LABEL_67:
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
          if ( v15 < 0 )
            return (unsigned int)v15;
LABEL_68:
          for ( i = 0; i < 0xAu; ++i )
          {
            if ( *((_QWORD *)this + 25) )
              break;
            Sleep(0xAu);
          }
          return (unsigned int)v15;
        }
      }
      else
      {
        v10 = *((_WORD *)this + 49);
        *(_WORD *)&v47[14] = v10;
      }
      v11 = (unsigned __int16)(v8 * (v10 >> 3));
      v12 = *((_QWORD *)this + 14);
      *(_WORD *)&v47[12] = v11;
      *(_DWORD *)&v47[8] = v9 * v11;
      v13 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v12 + 112LL))(v12, v47, v7);
      if ( (int)(v13 + 0x80000000) >= 0 && v13 != -2005401530 )
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 14) + 16LL))(*((_QWORD *)this + 14));
        v14 = (_QWORD *)((char *)this + 120);
        *((_QWORD *)this + 14) = 0;
        *((_QWORD *)this + 15) = 0;
        v15 = -2147418113;
        goto LABEL_29;
      }
      goto LABEL_22;
    }
  }
  return 2289570097LL;
}

```

## disassembly

```asm
0x18000f010  push    rbp
0x18000f012  push    rbx
0x18000f013  push    rsi
0x18000f014  lea     rbp, [rsp-30h]
0x18000f019  sub     rsp, 130h
0x18000f020  mov     rax, cs:__security_cookie
0x18000f027  xor     rax, rsp
0x18000f02a  mov     [rbp+40h+var_30], rax
0x18000f02e  cmp     qword ptr [rcx+18h], 0
0x18000f033  mov     rbx, rcx
0x18000f036  jz      loc_18000F621
0x18000f03c  cmp     qword ptr [rcx+68h], 0
0x18000f041  jnz     short loc_18000F04D
0x18000f043  mov     eax, 88781139h
0x18000f048  jmp     loc_18000F626
0x18000f04d  lea     rsi, [rcx+54h]
0x18000f051  mov     rdx, rsi; struct tWAVEFORMATEX *
0x18000f054  call    ?IsValidFormat@CDSLink@@AEAAHPEBUtWAVEFORMATEX@@@Z; CDSLink::IsValidFormat(tWAVEFORMATEX const *)
0x18000f059  test    eax, eax
0x18000f05b  jz      loc_18000F621
0x18000f061  cmp     qword ptr [rbx+38h], 0
0x18000f066  jnz     short loc_18000F072
0x18000f068  mov     eax, 88781170h
0x18000f06d  jmp     loc_18000F626
0x18000f072  cmp     dword ptr [rbx+0E0h], 0
0x18000f079  jz      short loc_18000F085
0x18000f07b  mov     eax, 88781132h
0x18000f080  jmp     loc_18000F626
0x18000f085  mov     [rsp+140h+arg_8], rdi
0x18000f08d  lea     rcx, [rbx+88h]; lpCriticalSection
0x18000f094  mov     [rsp+140h+arg_10], r12
0x18000f09c  mov     [rsp+140h+var_18], r14
0x18000f0a4  mov     [rsp+140h+var_20], r15
0x18000f0ac  call    cs:__imp_EnterCriticalSection
0x18000f0b2  mov     rcx, [rbx+80h]
0x18000f0b9  xor     r12d, r12d
0x18000f0bc  test    rcx, rcx
0x18000f0bf  jnz     loc_18000F272
0x18000f0c5  mov     rcx, [rbx+68h]
0x18000f0c9  lea     r8, [rbx+70h]
0x18000f0cd  xorps   xmm0, xmm0
0x18000f0d0  mov     [rsp+140h+var_D0], 28h ; '('
0x18000f0d8  xorps   xmm1, xmm1
0x18000f0db  mov     [rsp+140h+var_CC], 1
0x18000f0e3  movdqu  [rsp+140h+var_C8], xmm0
0x18000f0e9  xor     r9d, r9d
0x18000f0ec  lea     rdx, [rsp+140h+var_D0]
0x18000f0f1  movdqu  [rbp+40h+var_B8], xmm1
0x18000f0f6  mov     rax, [rcx]
0x18000f0f9  mov     rax, [rax+18h]
0x18000f0fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f102  test    eax, eax
0x18000f104  js      loc_18000F267
0x18000f10a  mov     rcx, [rbx+70h]
0x18000f10e  lea     rdx, [rbp+40h+var_A8]
0x18000f112  xor     eax, eax
0x18000f114  xorps   xmm0, xmm0
0x18000f117  mov     [rbp+40h+var_98], ax
0x18000f11b  xor     r9d, r9d
0x18000f11e  movups  [rbp+40h+var_A8], xmm0
0x18000f122  mov     rax, [rcx]
0x18000f125  mov     r8d, 12h
0x18000f12b  mov     rax, [rax+28h]
0x18000f12f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f134  test    eax, eax
0x18000f136  js      loc_18000F267
0x18000f13c  movzx   ecx, word ptr [rbx+56h]
0x18000f140  mov     r8d, r12d
0x18000f143  movzx   eax, word ptr [rbp+40h+var_A8+2]
0x18000f147  cmp     ax, cx
0x18000f14a  jnb     short loc_18000F159
0x18000f14c  movzx   eax, cx
0x18000f14f  mov     word ptr [rbp+40h+var_A8+2], cx
0x18000f153  mov     r8d, 1
0x18000f159  mov     ecx, [rbx+58h]
0x18000f15c  mov     edx, dword ptr [rbp+40h+var_A8+4]
0x18000f15f  cmp     edx, ecx
0x18000f161  jnb     short loc_18000F16E
0x18000f163  mov     edx, ecx
0x18000f165  mov     dword ptr [rbp+40h+var_A8+4], ecx
0x18000f168  mov     r8d, 1
0x18000f16e  movzx   r9d, word ptr [rbx+62h]
0x18000f173  movzx   ecx, word ptr [rbp+40h+var_A8+0Eh]
0x18000f177  cmp     cx, r9w
0x18000f17b  jnb     short loc_18000F187
0x18000f17d  movzx   ecx, r9w
0x18000f181  mov     word ptr [rbp+40h+var_A8+0Eh], cx
0x18000f185  jmp     short loc_18000F18C
0x18000f187  test    r8d, r8d
0x18000f18a  jz      short loc_18000F1F2
0x18000f18c  movzx   eax, ax
0x18000f18f  shr     cx, 3
0x18000f193  movzx   ecx, cx
0x18000f196  imul    ecx, eax
0x18000f199  movzx   eax, cx
0x18000f19c  mov     rcx, [rbx+70h]
0x18000f1a0  mov     word ptr [rbp+40h+var_A8+0Ch], ax
0x18000f1a4  imul    eax, edx
0x18000f1a7  lea     rdx, [rbp+40h+var_A8]
0x18000f1ab  mov     dword ptr [rbp+40h+var_A8+8], eax
0x18000f1ae  mov     rax, [rcx]
0x18000f1b1  mov     rax, [rax+70h]
0x18000f1b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1ba  mov     edx, 80000000h
0x18000f1bf  lea     ecx, [rax+rdx]
0x18000f1c2  test    edx, ecx
0x18000f1c4  jnz     short loc_18000F1F2
0x18000f1c6  cmp     eax, 88780046h
0x18000f1cb  jz      short loc_18000F1F2
0x18000f1cd  mov     rcx, [rbx+70h]
0x18000f1d1  mov     rax, [rcx]
0x18000f1d4  mov     rax, [rax+10h]
0x18000f1d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1dd  lea     r14, [rbx+78h]
0x18000f1e1  mov     [rbx+70h], r12
0x18000f1e5  mov     [r14], r12
0x18000f1e8  mov     esi, 8000FFFFh
0x18000f1ed  jmp     loc_18000F28B
0x18000f1f2  mov     eax, [rbx+5Ch]
0x18000f1f5  lea     r14, [rbx+78h]
0x18000f1f9  mov     rcx, [rbx+68h]
0x18000f1fd  lea     rdx, [rsp+140h+var_D0]
0x18000f202  add     eax, eax
0x18000f204  mov     dword ptr [rsp+140h+var_C8+4], r12d
0x18000f209  mov     dword ptr [rsp+140h+var_C8], eax
0x18000f20d  xorps   xmm0, xmm0
0x18000f210  movdqu  [rbp+40h+var_B8], xmm0
0x18000f215  mov     [rsp+140h+var_D0], 28h ; '('
0x18000f21d  xor     r9d, r9d
0x18000f220  mov     [rsp+140h+var_CC], 18000h
0x18000f228  mov     r8, r14
0x18000f22b  mov     qword ptr [rbp+40h+var_C8+8], rsi
0x18000f22f  mov     rax, [rcx]
0x18000f232  mov     rax, [rax+18h]
0x18000f236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f23b  test    eax, eax
0x18000f23d  js      short loc_18000F244
0x18000f23f  mov     esi, r12d
0x18000f242  jmp     short loc_18000F28B
0x18000f244  mov     rcx, [rbx+70h]
0x18000f248  mov     [r14], r12
0x18000f24b  test    rcx, rcx
0x18000f24e  jz      short loc_18000F260
0x18000f250  mov     rax, [rcx]
0x18000f253  mov     rax, [rax+10h]
0x18000f257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f25c  mov     [rbx+70h], r12
0x18000f260  mov     esi, 8000FFFFh
0x18000f265  jmp     short loc_18000F28B
0x18000f267  mov     esi, 8000FFFFh
0x18000f26c  lea     r14, [rbx+78h]
0x18000f270  jmp     short loc_18000F28B
0x18000f272  mov     [rbx+78h], rcx
0x18000f276  lea     r14, [rbx+78h]
0x18000f27a  mov     rax, [rcx]
0x18000f27d  mov     esi, 80004005h
0x18000f282  mov     rax, [rax+8]
0x18000f286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f28b  mov     rcx, [r14]
0x18000f28e  test    rcx, rcx
0x18000f291  jz      loc_18000F553
0x18000f297  xorps   xmm0, xmm0
0x18000f29a  mov     dword ptr [rbp+40h+var_A8], 14h
0x18000f2a1  movdqu  [rbp+40h+var_A8+4], xmm0
0x18000f2a6  mov     rax, [rcx]
0x18000f2a9  lea     rdx, [rbp+40h+var_A8]
0x18000f2ad  mov     rax, [rax+18h]
0x18000f2b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2b6  test    eax, eax
0x18000f2b8  js      loc_18000F54C
0x18000f2be  mov     rcx, [rbx+68h]
0x18000f2c2  lea     rdx, [rbp+40h+var_90]
0x18000f2c6  xorps   xmm0, xmm0
0x18000f2c9  mov     [rbp+40h+var_90], 60h ; '`'
0x18000f2d0  movups  xmmword ptr [rbp+40h+var_4C], xmm0
0x18000f2d4  movups  [rbp+40h+var_8C], xmm0
0x18000f2d8  movups  [rbp+40h+var_7C], xmm0
0x18000f2dc  movups  [rbp+40h+var_6C], xmm0
0x18000f2e0  movups  [rbp+40h+var_5C], xmm0
0x18000f2e4  movups  xmmword ptr [rbp+40h+var_4C+0Ch], xmm0
0x18000f2e8  mov     rax, [rcx]
0x18000f2eb  mov     rax, [rax+20h]
0x18000f2ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2f4  test    eax, eax
0x18000f2f6  js      loc_18000F54C
0x18000f2fc  test    byte ptr [rbp+40h+var_8C], 20h
0x18000f300  lea     r8, [rsp+140h+var_E8]; unsigned int *
0x18000f305  mov     eax, 50h ; 'P'
0x18000f30a  lea     rdx, aDslminlatency; "DSLMinLatency"
0x18000f311  mov     edi, 0F0h
0x18000f316  cmovz   edi, eax
0x18000f319  mov     [rsp+140h+var_E8], edi
0x18000f31d  call    ?GetRegValueDword@@YAHPEBD0PEAK@Z; GetRegValueDword(char const *,char const *,ulong *)
0x18000f322  movzx   ecx, word ptr [rbx+56h]
0x18000f326  lea     r9, [rsp+140h+var_D8]
0x18000f32b  mov     r8d, dword ptr [rbp+40h+var_A8+8]
0x18000f32f  test    eax, eax
0x18000f331  mov     [rsp+140h+var_108], r12d
0x18000f336  mov     eax, 10624DD3h
0x18000f33b  cmovnz  edi, [rsp+140h+var_E8]
0x18000f340  imul    edi, [rbx+5Ch]
0x18000f344  mov     [rbx+0D4h], r8d
0x18000f34b  mov     [rbx+0D0h], r12d
0x18000f352  mov     [rbx+0C0h], r12d
0x18000f359  mov     [rbx+0B8h], r12
0x18000f360  mov     [rsp+140h+var_D8], r12
0x18000f365  add     edi, 1F4h
0x18000f36b  mul     edi
0x18000f36d  mov     [rsp+140h+var_E0], r12
0x18000f372  shr     edx, 6
0x18000f375  shr     edx, cl
0x18000f377  shl     edx, cl
0x18000f379  mov     rcx, [r14]
0x18000f37c  mov     [rbx+0D8h], edx
0x18000f382  lea     rdx, [rsp+140h+Size+4]
0x18000f387  mov     [rsp+140h+var_110], rdx
0x18000f38c  lea     rdx, [rsp+140h+var_E0]
0x18000f391  mov     [rsp+140h+lpThreadId], rdx
0x18000f396  lea     rdx, [rsp+140h+Size]
0x18000f39b  mov     dword ptr [rsp+140h+Size], r12d
0x18000f3a0  mov     dword ptr [rsp+140h+Size+4], r12d
0x18000f3a5  mov     rax, [rcx]
0x18000f3a8  mov     qword ptr [rsp+140h+dwCreationFlags], rdx
0x18000f3ad  xor     edx, edx
0x18000f3af  mov     rax, [rax+58h]
0x18000f3b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3b8  test    eax, eax
0x18000f3ba  js      loc_18000F54C
0x18000f3c0  mov     r8d, dword ptr [rsp+140h+Size]; Size
0x18000f3c5  test    r8d, r8d
0x18000f3c8  jz      short loc_18000F3DB
0x18000f3ca  mov     rcx, [rsp+140h+var_D8]; void *
0x18000f3cf  xor     edx, edx; Val
0x18000f3d1  call    memset_0
0x18000f3d6  mov     r8d, dword ptr [rsp+140h+Size]
0x18000f3db  mov     edx, dword ptr [rsp+140h+Size+4]
0x18000f3df  test    edx, edx
0x18000f3e1  jz      short loc_18000F3FB
0x18000f3e3  mov     rcx, [rsp+140h+var_E0]; void *
0x18000f3e8  mov     r8d, edx; Size
0x18000f3eb  xor     edx, edx; Val
0x18000f3ed  call    memset_0
0x18000f3f2  mov     r8d, dword ptr [rsp+140h+Size]
0x18000f3f7  mov     edx, dword ptr [rsp+140h+Size+4]
0x18000f3fb  mov     rcx, [r14]
0x18000f3fe  mov     r9, [rsp+140h+var_E0]
0x18000f403  mov     [rsp+140h+dwCreationFlags], edx
0x18000f407  mov     rdx, [rsp+140h+var_D8]
0x18000f40c  mov     rax, [rcx]
0x18000f40f  mov     rax, [rax+98h]
0x18000f416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f41b  mov     rcx, [r14]
0x18000f41e  mov     r9d, 1
0x18000f424  xor     r8d, r8d
0x18000f427  xor     edx, edx
0x18000f429  mov     rax, [rcx]
0x18000f42c  mov     rax, [rax+60h]
0x18000f430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f435  test    eax, eax
0x18000f437  js      loc_18000F54C
0x18000f43d  lea     rcx, CriticalSection; lpCriticalSection
0x18000f444  call    cs:__imp_EnterCriticalSection
0x18000f44a  cmp     [rbx+0E0h], r12d
0x18000f451  jnz     loc_18000F52A
0x18000f457  cmp     cs:dword_18001E610, r12d
0x18000f45e  jnz     short loc_18000F4BA
0x18000f460  xor     r9d, r9d; lpName
0x18000f463  xor     r8d, r8d; bInitialState
0x18000f466  xor     edx, edx; bManualReset
0x18000f468  xor     ecx, ecx; lpEventAttributes
0x18000f46a  call    cs:__imp_CreateEventA
0x18000f470  mov     cs:hEvent, rax
0x18000f477  lea     r9, ?g_DSLinkList@@3VCDSLinkList@@A; lpParameter
0x18000f47e  lea     rax, ThreadId
0x18000f485  xor     edx, edx; dwStackSize
0x18000f487  mov     [rsp+140h+lpThreadId], rax; lpThreadId
0x18000f48c  lea     r8, SynthThread; lpStartAddress
0x18000f493  xor     ecx, ecx; lpThreadAttributes
0x18000f495  mov     [rsp+140h+dwCreationFlags], r12d; dwCreationFlags
0x18000f49a  call    cs:__imp_CreateThread
0x18000f4a0  mov     cs:hHandle, rax
0x18000f4a7  test    rax, rax
0x18000f4aa  jz      short loc_18000F4BA
0x18000f4ac  mov     edx, 0Fh; nPriority
0x18000f4b1  mov     rcx, rax; hThread
0x18000f4b4  call    cs:__imp_SetThreadPriority
0x18000f4ba  mov     r8, cs:?g_DSLinkList@@3VCDSLinkList@@A; CDSLinkList g_DSLinkList
0x18000f4c1  lea     rdx, [rbx+10h]
0x18000f4c5  test    rbx, rbx
0x18000f4c8  mov     rcx, rdx
0x18000f4cb  mov     rax, r8
0x18000f4ce  cmovz   rcx, r12
0x18000f4d2  test    r8, r8
0x18000f4d5  jz      short loc_18000F4E4
0x18000f4d7  cmp     rax, rcx
0x18000f4da  jz      short loc_18000F520
0x18000f4dc  mov     rax, [rax]
0x18000f4df  test    rax, rax
0x18000f4e2  jnz     short loc_18000F4D7
0x18000f4e4  inc     cs:dword_18001E610
  ... truncated ...
```
