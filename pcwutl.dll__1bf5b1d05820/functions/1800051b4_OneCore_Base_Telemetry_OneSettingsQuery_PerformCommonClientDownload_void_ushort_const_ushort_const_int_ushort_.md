# OneCore::Base::Telemetry::OneSettingsQuery::PerformCommonClientDownload(void *,ushort const *,ushort const *,int,ushort const *,ushort const *,ushort * *)

- ea: `0x1800051b4`
- end: `0x1800055eb`
- name: `?PerformCommonClientDownload@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAXPEBG1H11PEAPEAG@Z`
- size: `1079`
- prototype: `__int64 __usercall@<rax>(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this@<rcx>, void *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, int, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000354c`

## callees

- `0x180004ef4`
- `0x1800051b4`
- `0x180007ae0`
- `0x18001a010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180005441`
- `KERNEL32!HeapAlloc` at `0x180005564`
- `KERNEL32!HeapAlloc` at `0x180005441`
- `KERNEL32!HeapAlloc` at `0x180005564`
- `KERNEL32!GetProcessHeap` at `0x180005430`
- `KERNEL32!GetProcessHeap` at `0x180005553`
- `KERNEL32!GetProcessHeap` at `0x180005430`
- `KERNEL32!GetProcessHeap` at `0x180005553`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::PerformCommonClientDownload(
        __int64 (__fastcall **this)(const wchar_t *, __int64 *),
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        unsigned __int16 **a8)
{
  unsigned __int16 **v8; // r15
  int v13; // ebx
  const unsigned __int16 *v14; // rsi
  __int64 v15; // rax
  unsigned __int64 v16; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rsi
  HANDLE v21; // rax
  unsigned __int16 *v22; // rax
  int v24; // [rsp+40h] [rbp-41h] BYREF
  int v25; // [rsp+44h] [rbp-3Dh] BYREF
  const wchar_t *v26; // [rsp+48h] [rbp-39h] BYREF
  __int64 v27; // [rsp+50h] [rbp-31h] BYREF
  unsigned __int16 *v28; // [rsp+58h] [rbp-29h] BYREF
  unsigned __int16 *v29; // [rsp+60h] [rbp-21h] BYREF
  __int64 v30; // [rsp+68h] [rbp-19h] BYREF
  char *v31; // [rsp+70h] [rbp-11h] BYREF
  int v32; // [rsp+D0h] [rbp+4Fh] BYREF

  v8 = a8;
  v30 = 0;
  v26 = 0;
  v27 = 0;
  v32 = 0;
  v24 = 0;
  v25 = 0;
  v28 = 0;
  v31 = 0;
  v29 = 0;
  if ( a8 )
    *a8 = 0;
  v13 = this[231](L"OSQ", &v30);
  if ( v13 >= 0 )
  {
    v13 = ((__int64 (__fastcall *)(const wchar_t **))this[221])(&v26);
    if ( v13 >= 0 )
    {
      if ( !a5
        || (v13 = ((__int64 (__fastcall *)(const wchar_t *, __int64, __int64))this[223])(v26, 1, 1), v13 >= 0)
        && (v13 = this[223](v26, (__int64 *)2), v13 >= 0) )
      {
        if ( !a2 || (v13 = ((__int64 (__fastcall *)(const wchar_t *, __int64, void *))this[226])(v26, 1, a2), v13 >= 0) )
        {
          if ( !a3
            || (v13 = ((__int64 (__fastcall *)(const wchar_t *, __int64, const unsigned __int16 *))this[225])(
                        v26,
                        1,
                        a3),
                v13 >= 0) )
          {
            if ( !a4
              || (v13 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, const unsigned __int16 *))this[225])(
                          v26,
                          0,
                          a4),
                  v13 >= 0) )
            {
              v14 = a6;
              if ( !a6
                || (v13 = ((__int64 (__fastcall *)(const wchar_t *, __int64, __int64))this[224])(v26, 1, 1), v13 >= 0)
                && (v13 = ((__int64 (__fastcall *)(const wchar_t *, __int64, const unsigned __int16 *))this[225])(
                            v26,
                            3,
                            v14),
                    v13 >= 0) )
              {
                if ( !a7 || (v13 = this[225](v26, (__int64 *)4), v13 >= 0) )
                {
                  v13 = ((__int64 (__fastcall *)(__int64, char *, char *, const wchar_t *, const wchar_t *, __int64 *))this[233])(
                          v30,
                          (char *)this + 40,
                          (char *)this + 560,
                          L"v2.0",
                          v26,
                          &v27);
                  if ( v13 >= 0 )
                  {
                    v13 = ((__int64 (__fastcall *)(__int64, _QWORD, int *))this[228])(v27, 0, &v32);
                    if ( v13 >= 0 )
                    {
                      switch ( v32 )
                      {
                        case 200:
                          v13 = ((__int64 (__fastcall *)(__int64, _QWORD, unsigned __int16 **))this[230])(v27, 0, &v28);
                          if ( v13 < 0 )
                            break;
                          v15 = -1;
                          do
                            ++v15;
                          while ( v28[v15] );
                          v16 = (unsigned int)(v15 + 1);
                          ProcessHeap = GetProcessHeap();
                          v18 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2 * v16);
                          this[4] = (__int64 (__fastcall *)(const wchar_t *, __int64 *))v18;
                          if ( !v18 )
                            goto LABEL_26;
                          v13 = StringCchCopyW(v18, v16, v28);
                          if ( v13 >= 0 )
                          {
                            v13 = ((__int64 (__fastcall *)(__int64, _QWORD, char **))this[229])(v27, 0, &v31);
                            if ( v13 >= 0 )
                              v13 = OneCore::Base::Telemetry::OneSettingsQuery::ParseJsonResult(
                                      (OneCore::Base::Telemetry::OneSettingsQuery *)this,
                                      v31);
                          }
                          break;
                        case 304:
                          v13 = 1;
                          break;
                        case 407:
                          v13 = ((__int64 (__fastcall *)(__int64, __int64, int *))this[228])(v27, 2, &v24);
                          if ( v13 < 0 )
                            break;
                          v13 = ((__int64 (__fastcall *)(__int64, __int64, int *))this[228])(v27, 4, &v25);
                          if ( v13 < 0 )
                            break;
                          if ( !v8 || (v24 & 1) == 0 || v25 != 1 )
                          {
LABEL_44:
                            v13 = -2147467259;
                            break;
                          }
                          v13 = ((__int64 (__fastcall *)(__int64, __int64, unsigned __int16 **))this[230])(v27, 3, &v29);
                          if ( v13 >= 0 )
                          {
                            v19 = -1;
                            do
                              ++v19;
                            while ( v29[v19] );
                            v20 = (unsigned int)(v19 + 1);
                            v21 = GetProcessHeap();
                            v22 = (unsigned __int16 *)HeapAlloc(v21, 8u, 2 * v20);
                            *v8 = v22;
                            if ( !v22 )
                            {
LABEL_26:
                              v13 = -2147024882;
                              break;
                            }
                            v13 = StringCchCopyW(v22, (unsigned int)v20, v29);
                            if ( v13 >= 0 )
                              v13 = -2147024891;
                          }
                          break;
                        default:
                          goto LABEL_44;
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
  if ( v27 )
    ((void (*)(void))this[227])();
  if ( v26 )
    ((void (*)(void))this[222])();
  if ( v30 )
    ((void (*)(void))this[232])();
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800051b4  push    rbp
0x1800051b6  push    rbx
0x1800051b7  push    rsi
0x1800051b8  push    rdi
0x1800051b9  push    r12
0x1800051bb  push    r13
0x1800051bd  push    r14
0x1800051bf  push    r15
0x1800051c1  lea     rbp, [rsp-7]
0x1800051c6  sub     rsp, 88h
0x1800051cd  mov     r15, [rbp+3Fh+arg_38]
0x1800051d4  xor     r13d, r13d
0x1800051d7  mov     [rbp+3Fh+var_58], r13
0x1800051db  mov     r12, r9
0x1800051de  mov     [rbp+3Fh+var_78], r13
0x1800051e2  mov     r14, r8
0x1800051e5  mov     [rbp+3Fh+var_70], r13
0x1800051e9  mov     rsi, rdx
0x1800051ec  mov     [rbp+3Fh+arg_0], r13d
0x1800051f0  mov     rdi, rcx
0x1800051f3  mov     [rbp+3Fh+var_80], r13d
0x1800051f7  mov     [rbp+3Fh+var_7C], r13d
0x1800051fb  mov     [rbp+3Fh+var_68], r13
0x1800051ff  mov     [rbp+3Fh+var_50], r13
0x180005203  mov     [rbp+3Fh+var_60], r13
0x180005207  test    r15, r15
0x18000520a  jz      short loc_18000520F
0x18000520c  mov     [r15], r13
0x18000520f  mov     rax, [rdi+738h]
0x180005216  lea     rdx, [rbp+3Fh+var_58]
0x18000521a  lea     rcx, aOsq; "OSQ"
0x180005221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005226  mov     ebx, eax
0x180005228  test    eax, eax
0x18000522a  js      loc_180005596
0x180005230  mov     rax, [rdi+6E8h]
0x180005237  lea     rcx, [rbp+3Fh+var_78]
0x18000523b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005240  mov     ebx, eax
0x180005242  test    eax, eax
0x180005244  js      loc_180005596
0x18000524a  cmp     [rbp+3Fh+arg_20], r13d
0x18000524e  jz      short loc_180005293
0x180005250  mov     rcx, [rbp+3Fh+var_78]
0x180005254  mov     edx, 1
0x180005259  mov     rax, [rdi+6F8h]
0x180005260  mov     r8d, edx
0x180005263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005268  mov     ebx, eax
0x18000526a  test    eax, eax
0x18000526c  js      loc_180005596
0x180005272  mov     rcx, [rbp+3Fh+var_78]
0x180005276  xor     r8d, r8d
0x180005279  mov     rax, [rdi+6F8h]
0x180005280  lea     edx, [r8+2]
0x180005284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005289  mov     ebx, eax
0x18000528b  test    eax, eax
0x18000528d  js      loc_180005596
0x180005293  test    rsi, rsi
0x180005296  jz      short loc_1800052BA
0x180005298  mov     rcx, [rbp+3Fh+var_78]
0x18000529c  mov     r8, rsi
0x18000529f  mov     rax, [rdi+710h]
0x1800052a6  mov     edx, 1
0x1800052ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052b0  mov     ebx, eax
0x1800052b2  test    eax, eax
0x1800052b4  js      loc_180005596
0x1800052ba  test    r14, r14
0x1800052bd  jz      short loc_1800052E7
0x1800052bf  mov     rcx, [rbp+3Fh+var_78]
0x1800052c3  mov     r8, r14
0x1800052c6  mov     rax, [rdi+708h]
0x1800052cd  mov     r14d, 1
0x1800052d3  mov     edx, r14d
0x1800052d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052db  mov     ebx, eax
0x1800052dd  test    eax, eax
0x1800052df  js      loc_180005596
0x1800052e5  jmp     short loc_1800052ED
0x1800052e7  mov     r14d, 1
0x1800052ed  test    r12, r12
0x1800052f0  jz      short loc_180005311
0x1800052f2  mov     rcx, [rbp+3Fh+var_78]
0x1800052f6  mov     r8, r12
0x1800052f9  mov     rax, [rdi+708h]
0x180005300  xor     edx, edx
0x180005302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005307  mov     ebx, eax
0x180005309  test    eax, eax
0x18000530b  js      loc_180005596
0x180005311  mov     rsi, [rbp+3Fh+arg_28]
0x180005315  mov     r12d, 3
0x18000531b  test    rsi, rsi
0x18000531e  jz      short loc_180005360
0x180005320  mov     rcx, [rbp+3Fh+var_78]
0x180005324  mov     r8d, r14d
0x180005327  mov     rax, [rdi+700h]
0x18000532e  mov     edx, r14d
0x180005331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005336  mov     ebx, eax
0x180005338  test    eax, eax
0x18000533a  js      loc_180005596
0x180005340  mov     rcx, [rbp+3Fh+var_78]
0x180005344  mov     r8, rsi
0x180005347  mov     rax, [rdi+708h]
0x18000534e  mov     edx, r12d
0x180005351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005356  mov     ebx, eax
0x180005358  test    eax, eax
0x18000535a  js      loc_180005596
0x180005360  mov     r8, [rbp+3Fh+arg_30]
0x180005364  mov     esi, 4
0x180005369  test    r8, r8
0x18000536c  jz      short loc_18000538A
0x18000536e  mov     rcx, [rbp+3Fh+var_78]
0x180005372  mov     edx, esi
0x180005374  mov     rax, [rdi+708h]
0x18000537b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005380  mov     ebx, eax
0x180005382  test    eax, eax
0x180005384  js      loc_180005596
0x18000538a  mov     rcx, [rbp+3Fh+var_78]
0x18000538e  lea     rax, [rbp+3Fh+var_70]
0x180005392  mov     [rsp+0C0h+var_98], rax
0x180005397  lea     r8, [rdi+230h]
0x18000539e  mov     rax, [rdi+748h]
0x1800053a5  lea     rdx, [rdi+28h]
0x1800053a9  mov     [rsp+0C0h+var_A0], rcx
0x1800053ae  lea     r9, aV20; "v2.0"
0x1800053b5  mov     rcx, [rbp+3Fh+var_58]
0x1800053b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053be  mov     ebx, eax
0x1800053c0  test    eax, eax
0x1800053c2  js      loc_180005596
0x1800053c8  mov     rcx, [rbp+3Fh+var_70]
0x1800053cc  lea     r8, [rbp+3Fh+arg_0]
0x1800053d0  mov     rax, [rdi+720h]
0x1800053d7  xor     edx, edx
0x1800053d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053de  mov     ebx, eax
0x1800053e0  test    eax, eax
0x1800053e2  js      loc_180005596
0x1800053e8  mov     eax, [rbp+3Fh+arg_0]
0x1800053eb  cmp     eax, 0C8h
0x1800053f0  jnz     loc_1800054A6
0x1800053f6  mov     rcx, [rbp+3Fh+var_70]
0x1800053fa  lea     r8, [rbp+3Fh+var_68]
0x1800053fe  mov     rax, [rdi+730h]
0x180005405  xor     edx, edx
0x180005407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000540c  mov     ebx, eax
0x18000540e  test    eax, eax
0x180005410  js      loc_180005596
0x180005416  mov     rcx, [rbp+3Fh+var_68]
0x18000541a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000541e  inc     rax
0x180005421  cmp     [rcx+rax*2], r13w
0x180005426  jnz     short loc_18000541E
0x180005428  inc     eax
0x18000542a  mov     esi, eax
0x18000542c  lea     rbx, [rax+rax]
0x180005430  call    cs:__imp_GetProcessHeap
0x180005436  mov     r8, rbx; dwBytes
0x180005439  mov     edx, 8; dwFlags
0x18000543e  mov     rcx, rax; hHeap
0x180005441  call    cs:__imp_HeapAlloc
0x180005447  mov     [rdi+20h], rax
0x18000544b  test    rax, rax
0x18000544e  jnz     short loc_18000545A
0x180005450  mov     ebx, 8007000Eh
0x180005455  jmp     loc_180005596
0x18000545a  mov     r8, [rbp+3Fh+var_68]; unsigned __int16 *
0x18000545e  mov     rdx, rsi; unsigned __int64
0x180005461  mov     rcx, rax; unsigned __int16 *
0x180005464  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005469  mov     ebx, eax
0x18000546b  test    eax, eax
0x18000546d  js      loc_180005596
0x180005473  mov     rcx, [rbp+3Fh+var_70]
0x180005477  lea     r8, [rbp+3Fh+var_50]
0x18000547b  mov     rax, [rdi+728h]
0x180005482  xor     edx, edx
0x180005484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005489  mov     ebx, eax
0x18000548b  test    eax, eax
0x18000548d  js      loc_180005596
0x180005493  mov     rdx, [rbp+3Fh+var_50]; char *
0x180005497  mov     rcx, rdi; this
0x18000549a  call    ?ParseJsonResult@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAD@Z; OneCore::Base::Telemetry::OneSettingsQuery::ParseJsonResult(char *)
0x18000549f  mov     ebx, eax
0x1800054a1  jmp     loc_180005596
0x1800054a6  cmp     eax, 130h
0x1800054ab  jnz     short loc_1800054B5
0x1800054ad  mov     ebx, r14d
0x1800054b0  jmp     loc_180005596
0x1800054b5  cmp     eax, 197h
0x1800054ba  jnz     loc_180005591
0x1800054c0  mov     rcx, [rbp+3Fh+var_70]
0x1800054c4  lea     r8, [rbp+3Fh+var_80]
0x1800054c8  mov     rax, [rdi+720h]
0x1800054cf  mov     edx, 2
0x1800054d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054d9  mov     ebx, eax
0x1800054db  test    eax, eax
0x1800054dd  js      loc_180005596
0x1800054e3  mov     rcx, [rbp+3Fh+var_70]
0x1800054e7  lea     r8, [rbp+3Fh+var_7C]
0x1800054eb  mov     rax, [rdi+720h]
0x1800054f2  mov     edx, esi
0x1800054f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054f9  mov     ebx, eax
0x1800054fb  test    eax, eax
0x1800054fd  js      loc_180005596
0x180005503  test    r15, r15
0x180005506  jz      loc_180005591
0x18000550c  mov     eax, [rbp+3Fh+var_80]
0x18000550f  and     eax, r14d
0x180005512  test    al, al
0x180005514  jz      short loc_180005591
0x180005516  cmp     [rbp+3Fh+var_7C], r14d
0x18000551a  jnz     short loc_180005591
0x18000551c  mov     rcx, [rbp+3Fh+var_70]
0x180005520  lea     r8, [rbp+3Fh+var_60]
0x180005524  mov     rax, [rdi+730h]
0x18000552b  mov     edx, r12d
0x18000552e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005533  mov     ebx, eax
0x180005535  test    eax, eax
0x180005537  js      short loc_180005596
0x180005539  mov     rcx, [rbp+3Fh+var_60]
0x18000553d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005541  inc     rax
0x180005544  cmp     [rcx+rax*2], r13w
0x180005549  jnz     short loc_180005541
0x18000554b  inc     eax
0x18000554d  mov     esi, eax
0x18000554f  lea     rbx, [rax+rax]
0x180005553  call    cs:__imp_GetProcessHeap
0x180005559  mov     r8, rbx; dwBytes
0x18000555c  mov     edx, 8; dwFlags
0x180005561  mov     rcx, rax; hHeap
0x180005564  call    cs:__imp_HeapAlloc
0x18000556a  mov     [r15], rax
0x18000556d  test    rax, rax
0x180005570  jz      loc_180005450
0x180005576  mov     r8, [rbp+3Fh+var_60]; unsigned __int16 *
0x18000557a  mov     edx, esi; unsigned __int64
0x18000557c  mov     rcx, rax; unsigned __int16 *
0x18000557f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005584  mov     ebx, eax
0x180005586  test    eax, eax
0x180005588  js      short loc_180005596
0x18000558a  mov     ebx, 80070005h
0x18000558f  jmp     short loc_180005596
0x180005591  mov     ebx, 80004005h
0x180005596  mov     rcx, [rbp+3Fh+var_70]
0x18000559a  test    rcx, rcx
0x18000559d  jz      short loc_1800055AB
0x18000559f  mov     rax, [rdi+718h]
0x1800055a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055ab  mov     rcx, [rbp+3Fh+var_78]
0x1800055af  test    rcx, rcx
0x1800055b2  jz      short loc_1800055C0
0x1800055b4  mov     rax, [rdi+6F0h]
0x1800055bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055c0  mov     rcx, [rbp+3Fh+var_58]
0x1800055c4  test    rcx, rcx
0x1800055c7  jz      short loc_1800055D5
0x1800055c9  mov     rax, [rdi+740h]
0x1800055d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055d5  mov     eax, ebx
0x1800055d7  add     rsp, 88h
0x1800055de  pop     r15
0x1800055e0  pop     r14
0x1800055e2  pop     r13
0x1800055e4  pop     r12
0x1800055e6  pop     rdi
0x1800055e7  pop     rsi
0x1800055e8  pop     rbx
0x1800055e9  pop     rbp
0x1800055ea  retn
```
