# CreateDecoderForStream(IStream *,IImageDecoder * *,DecoderInitFlag)

- ea: `0x18000cf08`
- end: `0x18000d222`
- name: `?CreateDecoderForStream@@YAJPEAUIStream@@PEAPEAUIImageDecoder@@W4DecoderInitFlag@@@Z`
- size: `794`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000e134`
- `0x180014100`
- `0x1800145a4`
- `0x180151940`

## callees

- `0x18000cf08`
- `0x18000d2f0`
- `0x18000d3b8`
- `0x18000d448`
- `0x18000d4b0`
- `0x18001f950`
- `0x1800e9380`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d208`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d208`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000d14f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000d14f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cf58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d031`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cf58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d031`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cf76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d074`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cf76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d074`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000d00d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000d00d`

## string_xrefs

- `0x18000d1fe`: `CreateCodecInstance`

## pseudocode

```c
__int64 __fastcall CreateDecoderForStream(struct IStream *a1, _QWORD *a2, unsigned int a3)
{
  unsigned int v4; // edi
  int v5; // esi
  void *v6; // rsi
  int v7; // eax
  __int64 v8; // rdi
  int v9; // r14d
  INT_PTR (__stdcall *v10)(); // r14
  const WCHAR *v11; // r12
  struct CachedCodecInfo *DecoderWithHeader; // rdi
  FARPROC ProcAddress; // rax
  int v14; // edi
  HMODULE Library; // rax
  unsigned int v17; // [rsp+30h] [rbp-49h] BYREF
  __int64 v18; // [rsp+38h] [rbp-41h] BYREF
  void *v19; // [rsp+40h] [rbp-39h] BYREF
  int v20; // [rsp+48h] [rbp-31h]
  int v21; // [rsp+4Ch] [rbp-2Dh]
  unsigned int v22; // [rsp+50h] [rbp-29h]
  _QWORD *v23; // [rsp+58h] [rbp-21h]
  char v24; // [rsp+60h] [rbp-19h] BYREF

  v17 = 0;
  v21 = 0;
  v19 = &v24;
  v22 = a3;
  v23 = a2;
  v20 = 64;
  EnterCriticalSection(&ImagingCritSec::critSec);
  ReloadCachedCodecInfo();
  v4 = dword_1801B3764;
  LeaveCriticalSection(&ImagingCritSec::critSec);
  if ( !v4 )
    return 2289762310LL;
  if ( (unsigned int)GpTempBuffer::Realloc((GpTempBuffer *)&v19, v4) )
  {
    v5 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, 0, 0, 0);
    if ( v5 < 0 )
    {
      if ( v21 )
        GpFree(v19);
      return (unsigned int)v5;
    }
    else
    {
      v6 = v19;
      v7 = BlockingReadStream(a1, v19, v4, &v17);
      if ( !v17 )
      {
        v14 = -2147467259;
        if ( v7 < 0 )
          v14 = v7;
        goto LABEL_19;
      }
      v8 = -v17;
      while ( 1 )
      {
        v9 = (*(__int64 (__fastcall **)(struct IStream *, __int64, __int64))(*(_QWORD *)a1 + 40LL))(a1, v8, 1);
        if ( v9 != -2147483638 )
          break;
        Sleep(0);
      }
      if ( v9 >= 0 )
      {
        v10 = 0;
        v11 = 0;
        EnterCriticalSection(&ImagingCritSec::critSec);
        if ( (v22 & 2) != 0 && (DecoderWithHeader = FindDecoderWithHeader(v6, v17, 0x10000u)) != 0
          || (DecoderWithHeader = FindDecoderWithHeader(v6, v17, 0)) != 0 )
        {
          v10 = (INT_PTR (__stdcall *)())*((_QWORD *)DecoderWithHeader + 16);
          if ( !v10 )
            v11 = (const WCHAR *)*((_QWORD *)DecoderWithHeader + 5);
        }
        LeaveCriticalSection(&ImagingCritSec::critSec);
        if ( DecoderWithHeader )
        {
          v18 = 0;
          if ( v10 )
          {
            ProcAddress = v10;
          }
          else
          {
            Library = LoadLibraryExW(v11, 0, 0);
            if ( !Library || (ProcAddress = GetProcAddress(Library, "CreateCodecInstance")) == 0 )
            {
              v14 = -2005204983;
LABEL_19:
              if ( v21 )
                GpFree(v6);
              return (unsigned int)v14;
            }
          }
          v14 = ((__int64 (__fastcall *)(GUID *, __int64 *))ProcAddress)(&IID_IImageDecoder, &v18);
          if ( v14 >= 0 )
          {
            v14 = (*(__int64 (__fastcall **)(__int64, struct IStream *, _QWORD))(*(_QWORD *)v18 + 24LL))(v18, a1, v22);
            if ( v14 < 0 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 32LL))(v18);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            }
            else
            {
              *v23 = v18;
            }
          }
          goto LABEL_19;
        }
        if ( v21 )
          GpFree(v6);
        return 2289762310LL;
      }
      if ( v21 )
        GpFree(v6);
      return (unsigned int)v9;
    }
  }
  else
  {
    if ( v21 )
      GpFree(v19);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000cf08  mov     [rsp-8+arg_18], rsi
0x18000cf0d  push    rbp
0x18000cf0e  push    rdi
0x18000cf0f  push    r12
0x18000cf11  push    r13
0x18000cf13  push    r14
0x18000cf15  lea     rbp, [rsp-37h]
0x18000cf1a  sub     rsp, 0B0h
0x18000cf21  mov     rax, cs:__security_cookie
0x18000cf28  xor     rax, rsp
0x18000cf2b  mov     [rbp+57h+var_30], rax
0x18000cf2f  and     [rbp+57h+var_A0], 0
0x18000cf33  lea     rax, [rbp+57h+var_70]
0x18000cf37  and     [rbp+57h+var_84], 0
0x18000cf3b  mov     r13, rcx
0x18000cf3e  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000cf45  mov     [rbp+57h+var_90], rax
0x18000cf49  mov     [rbp+57h+var_80], r8d
0x18000cf4d  mov     [rbp+57h+var_78], rdx
0x18000cf51  mov     [rbp+57h+var_88], 40h ; '@'
0x18000cf58  call    cs:__imp_EnterCriticalSection
0x18000cf5f  nop     dword ptr [rax+rax+00h]
0x18000cf64  call    ?ReloadCachedCodecInfo@@YAXXZ; ReloadCachedCodecInfo(void)
0x18000cf69  mov     edi, cs:dword_1801B3764
0x18000cf6f  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000cf76  call    cs:__imp_LeaveCriticalSection
0x18000cf7d  nop     dword ptr [rax+rax+00h]
0x18000cf82  test    edi, edi
0x18000cf84  jz      loc_18000D122
0x18000cf8a  mov     edx, edi; unsigned int
0x18000cf8c  lea     rcx, [rbp+57h+var_90]; this
0x18000cf90  call    ?Realloc@GpTempBuffer@@QEAAHI@Z; GpTempBuffer::Realloc(uint)
0x18000cf95  test    eax, eax
0x18000cf97  jz      loc_18000D16E
0x18000cf9d  mov     rax, [r13+0]
0x18000cfa1  xor     r9d, r9d
0x18000cfa4  xor     r8d, r8d
0x18000cfa7  xor     edx, edx
0x18000cfa9  mov     rcx, r13
0x18000cfac  mov     rax, [rax+28h]
0x18000cfb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfb5  mov     esi, eax
0x18000cfb7  test    eax, eax
0x18000cfb9  js      loc_18000D187
0x18000cfbf  mov     rsi, [rbp+57h+var_90]
0x18000cfc3  lea     r9, [rbp+57h+var_A0]; unsigned int *
0x18000cfc7  mov     rdx, rsi; void *
0x18000cfca  mov     r8d, edi; unsigned int
0x18000cfcd  mov     rcx, r13; struct IStream *
0x18000cfd0  call    ?BlockingReadStream@@YAJPEAUIStream@@PEAXIPEAI@Z; BlockingReadStream(IStream *,void *,uint,uint *)
0x18000cfd5  cmp     [rbp+57h+var_A0], 0
0x18000cfd9  jz      loc_18000D19D
0x18000cfdf  mov     eax, [rbp+57h+var_A0]
0x18000cfe2  neg     eax
0x18000cfe4  movsxd  rdi, eax
0x18000cfe7  mov     rax, [r13+0]
0x18000cfeb  xor     r9d, r9d
0x18000cfee  mov     rdx, rdi
0x18000cff1  mov     rcx, r13
0x18000cff4  mov     rax, [rax+28h]
0x18000cff8  lea     r8d, [r9+1]
0x18000cffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d001  mov     r14d, eax
0x18000d004  cmp     eax, 8000000Ah
0x18000d009  jnz     short loc_18000D01B
0x18000d00b  xor     ecx, ecx; dwMilliseconds
0x18000d00d  call    cs:__imp_Sleep
0x18000d014  nop     dword ptr [rax+rax+00h]
0x18000d019  jmp     short loc_18000CFE7
0x18000d01b  test    r14d, r14d
0x18000d01e  js      loc_18000D109
0x18000d024  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d02b  xor     r14d, r14d
0x18000d02e  xor     r12d, r12d
0x18000d031  call    cs:__imp_EnterCriticalSection
0x18000d038  nop     dword ptr [rax+rax+00h]
0x18000d03d  test    byte ptr [rbp+57h+var_80], 2
0x18000d041  jnz     loc_18000D1C6
0x18000d047  mov     edx, [rbp+57h+var_A0]; unsigned int
0x18000d04a  xor     r8d, r8d; unsigned int
0x18000d04d  mov     rcx, rsi; void *
0x18000d050  call    ?FindDecoderWithHeader@@YAPEAUCachedCodecInfo@@PEBXII@Z; FindDecoderWithHeader(void const *,uint,uint)
0x18000d055  mov     rdi, rax
0x18000d058  test    rax, rax
0x18000d05b  jz      short loc_18000D06D
0x18000d05d  mov     r14, [rdi+80h]
0x18000d064  test    r14, r14
0x18000d067  jz      loc_18000D1E8
0x18000d06d  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d074  call    cs:__imp_LeaveCriticalSection
0x18000d07b  nop     dword ptr [rax+rax+00h]
0x18000d080  test    rdi, rdi
0x18000d083  jz      loc_18000D118
0x18000d089  and     [rbp+57h+var_98], 0
0x18000d08e  test    r14, r14
0x18000d091  jz      loc_18000D147
0x18000d097  mov     rax, r14
0x18000d09a  lea     rdx, [rbp+57h+var_98]
0x18000d09e  lea     rcx, IID_IImageDecoder
0x18000d0a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0aa  mov     edi, eax
0x18000d0ac  test    eax, eax
0x18000d0ae  js      short loc_18000D0D8
0x18000d0b0  mov     rcx, [rbp+57h+var_98]
0x18000d0b4  mov     rdx, r13
0x18000d0b7  mov     r8d, [rbp+57h+var_80]
0x18000d0bb  mov     rax, [rcx]
0x18000d0be  mov     rax, [rax+18h]
0x18000d0c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0c7  mov     rcx, [rbp+57h+var_98]
0x18000d0cb  mov     edi, eax
0x18000d0cd  test    eax, eax
0x18000d0cf  js      short loc_18000D129
0x18000d0d1  mov     rax, [rbp+57h+var_78]
0x18000d0d5  mov     [rax], rcx
0x18000d0d8  cmp     [rbp+57h+var_84], 0
0x18000d0dc  jnz     loc_18000D1AC
0x18000d0e2  mov     eax, edi
0x18000d0e4  mov     rcx, [rbp+57h+var_30]
0x18000d0e8  xor     rcx, rsp; StackCookie
0x18000d0eb  call    __security_check_cookie
0x18000d0f0  mov     rsi, [rsp+0D0h+arg_18]
0x18000d0f8  add     rsp, 0B0h
0x18000d0ff  pop     r14
0x18000d101  pop     r13
0x18000d103  pop     r12
0x18000d105  pop     rdi
0x18000d106  pop     rbp
0x18000d107  retn
0x18000d109  cmp     [rbp+57h+var_84], 0
0x18000d10d  jnz     loc_18000D1B9
0x18000d113  mov     eax, r14d
0x18000d116  jmp     short loc_18000D0E4
0x18000d118  cmp     [rbp+57h+var_84], 0
0x18000d11c  jnz     loc_18000D1F1
0x18000d122  mov     eax, 887B0006h
0x18000d127  jmp     short loc_18000D0E4
0x18000d129  mov     rax, [rcx]
0x18000d12c  mov     rax, [rax+20h]
0x18000d130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d135  mov     rcx, [rbp+57h+var_98]
0x18000d139  mov     rax, [rcx]
0x18000d13c  mov     rax, [rax+10h]
0x18000d140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d145  jmp     short loc_18000D0D8
0x18000d147  xor     r8d, r8d; dwFlags
0x18000d14a  xor     edx, edx; hFile
0x18000d14c  mov     rcx, r12; lpLibFileName
0x18000d14f  call    cs:__imp_LoadLibraryExW
0x18000d156  nop     dword ptr [rax+rax+00h]
0x18000d15b  test    rax, rax
0x18000d15e  jnz     loc_18000D1FE
0x18000d164  mov     edi, 887B0009h
0x18000d169  jmp     loc_18000D0D8
0x18000d16e  cmp     [rbp+57h+var_84], 0
0x18000d172  jz      short loc_18000D17D
0x18000d174  mov     rcx, [rbp+57h+var_90]
0x18000d178  call    GpFree
0x18000d17d  mov     eax, 8007000Eh
0x18000d182  jmp     loc_18000D0E4
0x18000d187  cmp     [rbp+57h+var_84], 0
0x18000d18b  jz      short loc_18000D196
0x18000d18d  mov     rcx, [rbp+57h+var_90]
0x18000d191  call    GpFree
0x18000d196  mov     eax, esi
0x18000d198  jmp     loc_18000D0E4
0x18000d19d  test    eax, eax
0x18000d19f  mov     edi, 80004005h
0x18000d1a4  cmovs   edi, eax
0x18000d1a7  jmp     loc_18000D0D8
0x18000d1ac  mov     rcx, rsi
0x18000d1af  call    GpFree
0x18000d1b4  jmp     loc_18000D0E2
0x18000d1b9  mov     rcx, rsi
0x18000d1bc  call    GpFree
0x18000d1c1  jmp     loc_18000D113
0x18000d1c6  mov     edx, [rbp+57h+var_A0]; unsigned int
0x18000d1c9  mov     r8d, 10000h; unsigned int
0x18000d1cf  mov     rcx, rsi; void *
0x18000d1d2  call    ?FindDecoderWithHeader@@YAPEAUCachedCodecInfo@@PEBXII@Z; FindDecoderWithHeader(void const *,uint,uint)
0x18000d1d7  mov     rdi, rax
0x18000d1da  test    rax, rax
0x18000d1dd  jnz     loc_18000D05D
0x18000d1e3  jmp     loc_18000D047
0x18000d1e8  mov     r12, [rdi+28h]
0x18000d1ec  jmp     loc_18000D06D
0x18000d1f1  mov     rcx, rsi
0x18000d1f4  call    GpFree
0x18000d1f9  jmp     loc_18000D122
0x18000d1fe  lea     rdx, ProcName; "CreateCodecInstance"
0x18000d205  mov     rcx, rax; hModule
0x18000d208  call    cs:__imp_GetProcAddress
0x18000d20f  nop     dword ptr [rax+rax+00h]
0x18000d214  test    rax, rax
0x18000d217  jz      loc_18000D164
0x18000d21d  jmp     loc_18000D09A
```
