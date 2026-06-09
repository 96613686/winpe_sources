# CCrashSignature::SetModuleInfo(void *,wchar_t const *,HINSTANCE__ *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,ushort * const,ulong *)

- ea: `0x180018800`
- end: `0x180018a66`
- name: `?SetModuleInfo@CCrashSignature@@AEAAJPEAXPEB_WPEAUHINSTANCE__@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@3QEAGPEAK@Z`
- size: `614`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180017498`

## callees

- `0x180009e04`
- `0x180009ed8`
- `0x180018800`
- `0x18003a164`
- `0x18003ae98`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018998`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018998`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001896d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001896d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018982`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018982`

## pseudocode

```c
__int64 __fastcall CCrashSignature::SetModuleInfo(
        __int64 a1,
        void *a2,
        unsigned __int64 a3,
        HINSTANCE a4,
        LPCWSTR *a5,
        _QWORD *a6,
        _WORD *a7,
        _DWORD *a8)
{
  __int64 v11; // rdi
  __int64 v12; // r8
  __int64 v13; // rax
  unsigned __int16 *v14; // rcx
  unsigned __int64 v15; // rax
  __int64 v16; // r8
  unsigned __int16 *v17; // rdx
  _WORD *v18; // rcx
  int TimestampModule; // eax
  int v20; // ebx
  HMODULE Library; // rax
  HMODULE v22; // rdi
  HINSTANCE v23; // rbx
  HANDLE CurrentProcess; // rax
  unsigned int v25; // ebx

  if ( a3 && a5 && a6 && a8 )
  {
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(a3 + 2 * v12) );
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a5, a3) )
      goto LABEL_33;
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)(a3 + 2 * v13) );
    v14 = (unsigned __int16 *)(a3 + 2 * v13);
    while ( 1 )
    {
      v17 = v14;
      if ( (unsigned __int64)v14 <= a3 )
        break;
      v15 = *--v14;
      LOWORD(v15) = v15 - 47;
      if ( (unsigned __int16)v15 <= 0x2Du )
      {
        v16 = 0x200000000801LL;
        if ( _bittest64(&v16, v15) )
          break;
      }
    }
    if ( v17 )
    {
      do
        ++v11;
      while ( v17[v11] );
    }
    else
    {
      v11 = 0;
    }
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                            a6,
                            v17,
                            v11) )
    {
      if ( (unsigned __int64)((__int64)(a6[1] - *a6) >> 1) > 0x40 )
      {
        v18 = (_WORD *)(*a6 + 128LL);
        a6[1] = v18;
        *v18 = 0;
      }
      TimestampModule = UtilGetTimestampModule(a2, a4);
      *a8 = TimestampModule;
      if ( !TimestampModule )
      {
        if ( *a5 )
        {
          v20 = 0;
          Library = LoadLibraryExW(*a5, 0, 2u);
          v22 = Library;
          if ( Library )
          {
            v23 = (HINSTANCE)((unsigned __int64)Library & 0xFFFFFFFFFFFFFFFCuLL);
            CurrentProcess = GetCurrentProcess();
            v20 = UtilGetTimestampModule(CurrentProcess, v23);
            FreeLibrary(v22);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
          v20 = 0;
        }
        *a8 = v20;
      }
      if ( (int)UtilGetFileInfo(*a5, 0) >= 0 )
      {
        *a7 = 0;
        a7[1] = 0;
        a7[2] = 0;
        a7[3] = 0;
      }
      return 0;
    }
    else
    {
LABEL_33:
      v25 = -2147024882;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids);
    }
    return v25;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180018800  push    rbx
0x180018802  push    rbp
0x180018803  push    rsi
0x180018804  push    rdi
0x180018805  push    r12
0x180018807  push    r13
0x180018809  push    r14
0x18001880b  push    r15
0x18001880d  sub     rsp, 78h
0x180018811  xorps   xmm0, xmm0
0x180018814  xor     eax, eax
0x180018816  xor     r13d, r13d
0x180018819  mov     [rsp+0B8h+var_58], eax
0x18001881d  mov     rbp, r9
0x180018820  mov     rbx, r8
0x180018823  mov     r12, rdx
0x180018826  movups  [rsp+0B8h+var_88], xmm0
0x18001882b  movups  [rsp+0B8h+var_78], xmm0
0x180018830  movups  [rsp+0B8h+var_68], xmm0
0x180018835  test    r8, r8
0x180018838  jz      loc_180018A22
0x18001883e  mov     r14, [rsp+0B8h+arg_20]
0x180018846  test    r14, r14
0x180018849  jz      loc_180018A22
0x18001884f  mov     rsi, [rsp+0B8h+arg_28]
0x180018857  test    rsi, rsi
0x18001885a  jz      loc_180018A22
0x180018860  mov     r15, [rsp+0B8h+arg_38]
0x180018868  test    r15, r15
0x18001886b  jz      loc_180018A22
0x180018871  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180018875  mov     r8, rdi
0x180018878  inc     r8
0x18001887b  cmp     [rbx+r8*2], r13w
0x180018880  jnz     short loc_180018878
0x180018882  mov     rdx, rbx
0x180018885  mov     rcx, r14
0x180018888  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18001888d  test    al, al
0x18001888f  jz      loc_1800189EB
0x180018895  mov     rax, rdi
0x180018898  inc     rax
0x18001889b  cmp     [rbx+rax*2], r13w
0x1800188a0  jnz     short loc_180018898
0x1800188a2  lea     rcx, [rbx+rax*2]
0x1800188a6  jmp     short loc_1800188C9
0x1800188a8  sub     rcx, 2
0x1800188ac  movzx   eax, word ptr [rcx]
0x1800188af  sub     ax, 2Fh ; '/'
0x1800188b3  cmp     ax, 2Dh ; '-'
0x1800188b7  ja      short loc_1800188C9
0x1800188b9  mov     r8, 200000000801h
0x1800188c3  bt      r8, rax
0x1800188c7  jb      short loc_1800188D1
0x1800188c9  mov     rdx, rcx
0x1800188cc  cmp     rcx, rbx
0x1800188cf  ja      short loc_1800188A8
0x1800188d1  test    rdx, rdx
0x1800188d4  jz      short loc_1800188E2
0x1800188d6  inc     rdi
0x1800188d9  cmp     [rdx+rdi*2], r13w
0x1800188de  jnz     short loc_1800188D6
0x1800188e0  jmp     short loc_1800188E5
0x1800188e2  mov     rdi, r13
0x1800188e5  mov     r8, rdi
0x1800188e8  mov     rcx, rsi
0x1800188eb  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800188f0  test    al, al
0x1800188f2  jz      loc_1800189EB
0x1800188f8  mov     rcx, [rsi]
0x1800188fb  mov     rax, [rsi+8]
0x1800188ff  sub     rax, rcx
0x180018902  sar     rax, 1
0x180018905  cmp     rax, 40h ; '@'
0x180018909  jbe     short loc_180018917
0x18001890b  sub     rcx, 0FFFFFFFFFFFFFF80h
0x18001890f  mov     [rsi+8], rcx
0x180018913  mov     [rcx], r13w
0x180018917  mov     rdx, rbp; lpBaseAddress
0x18001891a  mov     rcx, r12; hProcess
0x18001891d  call    ?UtilGetTimestampModule@@YAKPEAXPEAUHINSTANCE__@@@Z; UtilGetTimestampModule(void *,HINSTANCE__ *)
0x180018922  mov     [r15], eax
0x180018925  test    eax, eax
0x180018927  jnz     short loc_1800189A1
0x180018929  mov     rcx, [r14]; lpLibFileName
0x18001892c  test    rcx, rcx
0x18001892f  jnz     short loc_180018964
0x180018931  mov     rcx, cs:WPP_GLOBAL_Control
0x180018938  lea     rax, WPP_GLOBAL_Control
0x18001893f  cmp     rcx, rax
0x180018942  jz      short loc_18001895F
0x180018944  test    byte ptr [rcx+1Ch], 1
0x180018948  jz      short loc_18001895F
0x18001894a  mov     rcx, [rcx+10h]
0x18001894e  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180018955  mov     edx, 42h ; 'B'
0x18001895a  call    WPP_SF_
0x18001895f  mov     ebx, r13d
0x180018962  jmp     short loc_18001899E
0x180018964  xor     edx, edx; hFile
0x180018966  mov     ebx, r13d
0x180018969  lea     r8d, [rdx+2]; dwFlags
0x18001896d  call    cs:__imp_LoadLibraryExW
0x180018973  mov     rdi, rax
0x180018976  test    rax, rax
0x180018979  jz      short loc_18001899E
0x18001897b  mov     rbx, rax
0x18001897e  and     rbx, 0FFFFFFFFFFFFFFFCh
0x180018982  call    cs:__imp_GetCurrentProcess
0x180018988  mov     rcx, rax; hProcess
0x18001898b  mov     rdx, rbx; lpBaseAddress
0x18001898e  call    ?UtilGetTimestampModule@@YAKPEAXPEAUHINSTANCE__@@@Z; UtilGetTimestampModule(void *,HINSTANCE__ *)
0x180018993  mov     rcx, rdi; hLibModule
0x180018996  mov     ebx, eax
0x180018998  call    cs:__imp_FreeLibrary
0x18001899e  mov     [r15], ebx
0x1800189a1  mov     rcx, [r14]; lpwstrFilename
0x1800189a4  lea     rdx, [rsp+0B8h+var_88]
0x1800189a9  xor     r9d, r9d
0x1800189ac  mov     [rsp+0B8h+var_98], r13d; int
0x1800189b1  xor     r8d, r8d
0x1800189b4  call    ?UtilGetFileInfo@@YAJPEB_WPEAUtagVS_FIXEDFILEINFO@@QEBQEB_WQEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@K@Z; UtilGetFileInfo(wchar_t const *,tagVS_FIXEDFILEINFO *,wchar_t const * const * const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> * const,ulong)
0x1800189b9  test    eax, eax
0x1800189bb  js      short loc_1800189E6
0x1800189bd  mov     rdx, [rsp+0B8h+arg_30]
0x1800189c5  mov     ecx, dword ptr [rsp+0B8h+var_88+8]
0x1800189c9  mov     eax, ecx
0x1800189cb  shr     eax, 10h
0x1800189ce  mov     [rdx], ax
0x1800189d1  mov     [rdx+2], cx
0x1800189d5  mov     ecx, dword ptr [rsp+0B8h+var_88+0Ch]
0x1800189d9  mov     eax, ecx
0x1800189db  shr     eax, 10h
0x1800189de  mov     [rdx+4], ax
0x1800189e2  mov     [rdx+6], cx
0x1800189e6  mov     ebx, r13d
0x1800189e9  jmp     short loc_180018A1E
0x1800189eb  mov     ebx, 8007000Eh
0x1800189f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800189f7  lea     rax, WPP_GLOBAL_Control
0x1800189fe  cmp     rcx, rax
0x180018a01  jz      short loc_180018A1E
0x180018a03  test    byte ptr [rcx+1Ch], 1
0x180018a07  jz      short loc_180018A1E
0x180018a09  mov     rcx, [rcx+10h]
0x180018a0d  lea     r8, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids
0x180018a14  mov     edx, 0Fh
0x180018a19  call    WPP_SF_
0x180018a1e  mov     eax, ebx
0x180018a20  jmp     short loc_180018A55
0x180018a22  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a29  lea     rax, WPP_GLOBAL_Control
0x180018a30  cmp     rcx, rax
0x180018a33  jz      short loc_180018A50
0x180018a35  test    byte ptr [rcx+1Ch], 1
0x180018a39  jz      short loc_180018A50
0x180018a3b  mov     rcx, [rcx+10h]
0x180018a3f  lea     r8, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids
0x180018a46  mov     edx, 0Eh
0x180018a4b  call    WPP_SF_
0x180018a50  mov     eax, 80070057h
0x180018a55  add     rsp, 78h
0x180018a59  pop     r15
0x180018a5b  pop     r14
0x180018a5d  pop     r13
0x180018a5f  pop     r12
0x180018a61  pop     rdi
0x180018a62  pop     rsi
0x180018a63  pop     rbp
0x180018a64  pop     rbx
0x180018a65  retn
```
