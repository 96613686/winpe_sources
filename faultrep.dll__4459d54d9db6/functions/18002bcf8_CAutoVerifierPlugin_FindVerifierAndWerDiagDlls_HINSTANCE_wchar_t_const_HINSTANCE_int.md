# CAutoVerifierPlugin::FindVerifierAndWerDiagDlls(HINSTANCE__ * *,wchar_t const * *,HINSTANCE__ * *,int *)

- ea: `0x18002bcf8`
- end: `0x18002bf4b`
- name: `?FindVerifierAndWerDiagDlls@CAutoVerifierPlugin@@AEAAJPEAPEAUHINSTANCE__@@PEAPEB_W0PEAH@Z`
- size: `595`
- prototype: `__int64 __fastcall(CAutoVerifierPlugin *__hidden this, HINSTANCE *, const wchar_t **, HINSTANCE *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18002c6f0`

## callees

- `0x180002890`
- `0x180003474`
- `0x180009ed8`
- `0x18002bcf8`
- `0x180049280`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002be5a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002be88`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002beb2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002be5a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002be88`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002beb2`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18002bde8`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18002bde8`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcessModules` at `0x18002bd98`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcessModules` at `0x18002bd98`

## string_xrefs

- `0x18002be50`: `vrfcore.dll`
- `0x18002be6c`: `vrfcore.dll`
- `0x18002be7e`: `verifier.dll`
- `0x18002be97`: `verifier.dll`
- `0x18002bea8`: `werdiagcontroller.dll`

## pseudocode

```c
__int64 __fastcall CAutoVerifierPlugin::FindVerifierAndWerDiagDlls(
        CAutoVerifierPlugin *this,
        HINSTANCE *a2,
        const wchar_t **a3,
        HINSTANCE *a4,
        int *a5)
{
  void *v9; // rcx
  DWORD v10; // esi
  HMODULE v11; // rbx
  const wchar_t *v12; // r12
  DWORD v13; // r14d
  __int64 v14; // rax
  WCHAR *v15; // rcx
  unsigned __int64 v16; // rax
  __int64 v17; // rdx
  WCHAR *v18; // rdi
  DWORD cbNeeded; // [rsp+20h] [rbp-E0h] BYREF
  CAutoVerifierPlugin *v21; // [rsp+28h] [rbp-D8h]
  HINSTANCE *v22; // [rsp+30h] [rbp-D0h]
  HINSTANCE *v23; // [rsp+38h] [rbp-C8h]
  const wchar_t **v24; // [rsp+40h] [rbp-C0h]
  HMODULE hModule[512]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Filename[264]; // [rsp+1050h] [rbp+F50h] BYREF

  v24 = a3;
  v23 = a2;
  v21 = this;
  v22 = a4;
  memset_0(hModule, 0, sizeof(hModule));
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v9 = (void *)*((_QWORD *)this + 98);
  cbNeeded = 0;
  Filename[0] = 0;
  if ( K32EnumProcessModules(v9, hModule, 0x1000u, &cbNeeded) && cbNeeded <= 0x1000 )
  {
    v10 = cbNeeded >> 3;
    v11 = 0;
    v12 = 0;
    v13 = 0;
    if ( !(cbNeeded >> 3) )
      return 2147942526LL;
    do
    {
      if ( K32GetModuleFileNameExW(*((HANDLE *)v21 + 98), hModule[v13], Filename, 0x104u) )
      {
        v14 = -1;
        do
          ++v14;
        while ( Filename[v14] );
        v15 = &Filename[v14];
        while ( 1 )
        {
          v18 = v15;
          if ( v15 <= Filename )
            break;
          v16 = *--v15;
          LOWORD(v16) = v16 - 47;
          if ( (unsigned __int16)v16 <= 0x2Du )
          {
            v17 = 0x200000000801LL;
            if ( _bittest64(&v17, v16) )
              break;
          }
        }
        if ( v18 )
        {
          if ( (unsigned int)_o__wcsicmp(v18, L"vrfcore.dll") )
          {
            if ( v11 || (unsigned int)_o__wcsicmp(v18, L"verifier.dll") )
            {
              if ( !(unsigned int)_o__wcsicmp(v18, L"werdiagcontroller.dll") )
                *v22 = hModule[v13];
            }
            else
            {
              v11 = hModule[v13];
              v12 = L"verifier.dll";
              *a5 = 1;
            }
          }
          else
          {
            v11 = hModule[v13];
            v12 = L"vrfcore.dll";
            *a5 = 0;
          }
        }
      }
      ++v13;
    }
    while ( v13 < v10 );
    if ( v11 )
    {
      *v23 = v11;
      *v24 = v12;
      return 0;
    }
    else
    {
      return 2147942526LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x18002bcf8  push    rbp
0x18002bcfa  push    rbx
0x18002bcfb  push    rsi
0x18002bcfc  push    rdi
0x18002bcfd  push    r12
0x18002bcff  push    r13
0x18002bd01  push    r14
0x18002bd03  push    r15
0x18002bd05  lea     rbp, [rsp-1178h]
0x18002bd0d  mov     eax, 1278h
0x18002bd12  call    _alloca_probe
0x18002bd17  sub     rsp, rax
0x18002bd1a  mov     rax, cs:__security_cookie
0x18002bd21  xor     rax, rsp
0x18002bd24  mov     [rbp+11B0h+var_50], rax
0x18002bd2b  mov     r13, [rbp+11B0h+arg_20]
0x18002bd32  mov     rdi, r8
0x18002bd35  mov     [rsp+12B0h+var_1270], r8
0x18002bd3a  mov     rbx, rdx
0x18002bd3d  mov     [rsp+12B0h+var_1278], rdx
0x18002bd42  mov     r14, rcx
0x18002bd45  mov     [rsp+12B0h+var_1288], rcx
0x18002bd4a  mov     r12d, 1000h
0x18002bd50  mov     r8d, r12d; Size
0x18002bd53  mov     [rsp+12B0h+var_1280], r9
0x18002bd58  xor     edx, edx; Val
0x18002bd5a  lea     rcx, [rsp+12B0h+hModule]; void *
0x18002bd5f  mov     rsi, r9
0x18002bd62  call    memset_0
0x18002bd67  xor     r15d, r15d
0x18002bd6a  lea     r9, [rsp+12B0h+cbNeeded]; lpcbNeeded
0x18002bd6f  mov     [rbx], r15
0x18002bd72  lea     rdx, [rsp+12B0h+hModule]; lphModule
0x18002bd77  mov     [rdi], r15
0x18002bd7a  mov     r8d, r12d; cb
0x18002bd7d  mov     [rsi], r15
0x18002bd80  mov     [r13+0], r15d
0x18002bd84  mov     rcx, [r14+310h]; hProcess
0x18002bd8b  mov     [rsp+12B0h+cbNeeded], r15d
0x18002bd90  mov     [rbp+11B0h+Filename], r15w
0x18002bd98  call    cs:__imp_K32EnumProcessModules
0x18002bd9e  test    eax, eax
0x18002bda0  jz      loc_18002BEF5
0x18002bda6  mov     esi, [rsp+12B0h+cbNeeded]
0x18002bdaa  cmp     esi, r12d
0x18002bdad  ja      loc_18002BEF5
0x18002bdb3  shr     esi, 3
0x18002bdb6  mov     ebx, r15d
0x18002bdb9  mov     r12d, r15d
0x18002bdbc  mov     r14d, r15d
0x18002bdbf  test    esi, esi
0x18002bdc1  jz      loc_18002BEEE
0x18002bdc7  mov     rax, [rsp+12B0h+var_1288]
0x18002bdcc  lea     r8, [rbp+11B0h+Filename]; lpFilename
0x18002bdd3  mov     r15d, r14d
0x18002bdd6  mov     r9d, 104h; nSize
0x18002bddc  mov     rcx, [rax+310h]; hProcess
0x18002bde3  mov     rdx, [rsp+r15*8+12B0h+hModule]; hModule
0x18002bde8  call    cs:__imp_K32GetModuleFileNameExW
0x18002bdee  xor     r8d, r8d
0x18002bdf1  test    eax, eax
0x18002bdf3  jz      loc_18002BEC9
0x18002bdf9  lea     rcx, [rbp+11B0h+Filename]
0x18002be00  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002be04  inc     rax
0x18002be07  cmp     [rcx+rax*2], r8w
0x18002be0c  jnz     short loc_18002BE04
0x18002be0e  lea     rcx, [rbp+11B0h+Filename]
0x18002be15  lea     rcx, [rcx+rax*2]
0x18002be19  jmp     short loc_18002BE3C
0x18002be1b  sub     rcx, 2
0x18002be1f  movzx   eax, word ptr [rcx]
0x18002be22  sub     ax, 2Fh ; '/'
0x18002be26  cmp     ax, 2Dh ; '-'
0x18002be2a  ja      short loc_18002BE3C
0x18002be2c  mov     rdx, 200000000801h
0x18002be36  bt      rdx, rax
0x18002be3a  jb      short loc_18002BE4B
0x18002be3c  lea     rax, [rbp+11B0h+Filename]
0x18002be43  mov     rdi, rcx
0x18002be46  cmp     rcx, rax
0x18002be49  ja      short loc_18002BE1B
0x18002be4b  test    rdi, rdi
0x18002be4e  jz      short loc_18002BEC9
0x18002be50  lea     rdx, aVrfcoreDll; "vrfcore.dll"
0x18002be57  mov     rcx, rdi
0x18002be5a  call    cs:__imp__o__wcsicmp
0x18002be60  xor     r8d, r8d
0x18002be63  test    eax, eax
0x18002be65  jnz     short loc_18002BE79
0x18002be67  mov     rbx, [rsp+r15*8+12B0h+hModule]
0x18002be6c  lea     r12, aVrfcoreDll; "vrfcore.dll"
0x18002be73  mov     [r13+0], r8d
0x18002be77  jmp     short loc_18002BEC9
0x18002be79  test    rbx, rbx
0x18002be7c  jnz     short loc_18002BEA8
0x18002be7e  lea     rdx, aVerifierDll; "verifier.dll"
0x18002be85  mov     rcx, rdi
0x18002be88  call    cs:__imp__o__wcsicmp
0x18002be8e  test    eax, eax
0x18002be90  jnz     short loc_18002BEA8
0x18002be92  mov     rbx, [rsp+r15*8+12B0h+hModule]
0x18002be97  lea     r12, aVerifierDll; "verifier.dll"
0x18002be9e  mov     dword ptr [r13+0], 1
0x18002bea6  jmp     short loc_18002BEC9
0x18002bea8  lea     rdx, aWerdiagcontrol; "werdiagcontroller.dll"
0x18002beaf  mov     rcx, rdi
0x18002beb2  call    cs:__imp__o__wcsicmp
0x18002beb8  test    eax, eax
0x18002beba  jnz     short loc_18002BEC9
0x18002bebc  mov     rcx, [rsp+12B0h+var_1280]
0x18002bec1  mov     rax, [rsp+r15*8+12B0h+hModule]
0x18002bec6  mov     [rcx], rax
0x18002bec9  inc     r14d
0x18002becc  cmp     r14d, esi
0x18002becf  jb      loc_18002BDC7
0x18002bed5  test    rbx, rbx
0x18002bed8  jz      short loc_18002BEEE
0x18002beda  mov     rax, [rsp+12B0h+var_1278]
0x18002bedf  mov     [rax], rbx
0x18002bee2  mov     rax, [rsp+12B0h+var_1270]
0x18002bee7  mov     [rax], r12
0x18002beea  xor     eax, eax
0x18002beec  jmp     short loc_18002BF28
0x18002beee  mov     eax, 8007007Eh
0x18002bef3  jmp     short loc_18002BF28
0x18002bef5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002befc  lea     rax, WPP_GLOBAL_Control
0x18002bf03  cmp     rcx, rax
0x18002bf06  jz      short loc_18002BF23
0x18002bf08  test    byte ptr [rcx+1Ch], 1
0x18002bf0c  jz      short loc_18002BF23
0x18002bf0e  mov     rcx, [rcx+10h]
0x18002bf12  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x18002bf19  mov     edx, 0Eh
0x18002bf1e  call    WPP_SF_
0x18002bf23  mov     eax, 80004005h
0x18002bf28  mov     rcx, [rbp+11B0h+var_50]
0x18002bf2f  xor     rcx, rsp; StackCookie
0x18002bf32  call    __security_check_cookie
0x18002bf37  add     rsp, 1278h
0x18002bf3e  pop     r15
0x18002bf40  pop     r14
0x18002bf42  pop     r13
0x18002bf44  pop     r12
0x18002bf46  pop     rdi
0x18002bf47  pop     rsi
0x18002bf48  pop     rbx
0x18002bf49  pop     rbp
0x18002bf4a  retn
```
