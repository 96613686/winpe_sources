# ShowHelp(ushort const *,ushort const *)

- ea: `0x140008300`
- end: `0x140008662`
- name: `?ShowHelp@@YAHPEBG0@Z`
- size: `866`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1400011e4`

## callees

- `0x14000810c`
- `0x140008300`
- `0x1400088c0`
- `0x140009820`
- `0x14000a010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x1400083df`
- `KERNEL32!GetModuleFileNameW` at `0x1400083df`
- `KERNEL32!GlobalAlloc` at `0x14000845c`
- `KERNEL32!GlobalAlloc` at `0x14000845c`
- `KERNEL32!GlobalFree` at `0x140008494`
- `KERNEL32!GlobalFree` at `0x1400085c9`
- `KERNEL32!GlobalFree` at `0x1400085f1`
- `KERNEL32!GlobalFree` at `0x140008613`
- `KERNEL32!GlobalFree` at `0x140008638`
- `KERNEL32!GlobalFree` at `0x140008494`
- `KERNEL32!GlobalFree` at `0x1400085c9`
- `KERNEL32!GlobalFree` at `0x1400085f1`
- `KERNEL32!GlobalFree` at `0x140008613`
- `KERNEL32!GlobalFree` at `0x140008638`
- `msi!__imp_MsiLoadStringW` at `0x140008399`
- `msi!__imp_MsiLoadStringW` at `0x140008399`
- `msi!__imp_MsiMessageBoxExW` at `0x1400085ba`
- `msi!__imp_MsiMessageBoxExW` at `0x1400085ba`

## pseudocode

```c
__int64 __fastcall ShowHelp(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  int StringW; // r14d
  int v3; // esi
  int v4; // eax
  char *p_hMem; // rcx
  char *v6; // r15
  unsigned int v7; // r9d
  unsigned int v8; // edx
  int v9; // eax
  __int64 v11; // [rsp+20h] [rbp-118h]
  int v12; // [rsp+28h] [rbp-110h]
  int v13; // [rsp+40h] [rbp-F8h] BYREF
  _DWORD v14[3]; // [rsp+44h] [rbp-F4h] BYREF
  __int64 v15; // [rsp+50h] [rbp-E8h] BYREF
  HGLOBAL v16; // [rsp+58h] [rbp-E0h] BYREF
  int v17; // [rsp+60h] [rbp-D8h]
  char v18; // [rsp+68h] [rbp-D0h] BYREF
  LPWSTR lpFilename; // [rsp+70h] [rbp-C8h] BYREF
  int v20; // [rsp+78h] [rbp-C0h]
  char v21; // [rsp+80h] [rbp-B8h] BYREF
  char *v22; // [rsp+88h] [rbp-B0h]
  int v23; // [rsp+90h] [rbp-A8h]
  char hMem; // [rsp+98h] [rbp-A0h] BYREF
  HGLOBAL v25; // [rsp+A0h] [rbp-98h] BYREF
  int v26; // [rsp+A8h] [rbp-90h]
  char v27; // [rsp+B0h] [rbp-88h] BYREF
  unsigned __int16 v28[32]; // [rsp+C0h] [rbp-78h] BYREF

  v26 = 1;
  v25 = &v27;
  v17 = 1;
  v16 = &v18;
  if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v25, 5000)
    || !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v16, 5000) )
  {
    goto LABEL_30;
  }
  StringW = MsiLoadStringW(-1, 10, v25, (unsigned int)v26, 0);
  v13 = StringW;
  v20 = 1;
  lpFilename = (LPWSTR)&v21;
  if ( (unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&lpFilename, 260) )
  {
    if ( GetModuleFileNameW(g_hInstance, lpFilename, 0x104u) )
    {
      lpFilename[259] = 0;
      v14[0] = 0;
      v3 = ((__int64 (__fastcall *)(LPWSTR, _DWORD *))VERSION::GetFileVersionInfoSizeW)(lpFilename, v14);
      v14[1] = v3;
      if ( v3 )
      {
        v4 = 1;
        v23 = 1;
        p_hMem = &hMem;
        v22 = &hMem;
        if ( v3 <= 1 )
        {
          v6 = &hMem;
        }
        else
        {
          v6 = (char *)GlobalAlloc(0x40u, v3);
          v4 = v23;
          p_hMem = v22;
        }
        if ( !v6 )
        {
          if ( v4 > 1 )
            goto LABEL_25;
          goto LABEL_26;
        }
        if ( p_hMem != &hMem )
          GlobalFree(p_hMem);
        v22 = v6;
        v23 = v3;
        if ( (unsigned int)((__int64 (__fastcall *)(LPWSTR, _QWORD, _QWORD, char *))VERSION::GetFileVersionInfoW)(
                             lpFilename,
                             v14[0],
                             (unsigned int)v3,
                             v6) )
        {
          v13 = 0;
          v15 = 0;
          if ( !(unsigned int)((__int64 (__fastcall *)(char *, const wchar_t *, __int64 *, int *))VERSION::VerQueryValueW)(
                                v22,
                                L"\\",
                                &v15,
                                &v13)
            || !v13 )
          {
            goto LABEL_16;
          }
          v7 = *(_DWORD *)(v15 + 8);
          v8 = *(_DWORD *)(v15 + 12);
        }
        else
        {
          v7 = 0;
          v8 = 0;
        }
        LODWORD(v11) = (unsigned __int16)v7;
        if ( (int)StringCchPrintfW(v28, 0x20u, L"%d.%d.%.4d.%d", HIWORD(v7), v11, HIWORD(v8), (unsigned __int16)v8) >= 0 )
        {
          StringCchPrintfW((unsigned __int16 *)v16, v17, (const unsigned __int16 *)v25, v28);
          if ( StringW == 1256 || (v9 = 105, StringW == 1255) )
            v9 = 120;
          LOWORD(v12) = 0;
          MsiMessageBoxExW(0, v16, 0, 0, StringW, v12, v9);
        }
LABEL_16:
        if ( v23 > 1 )
        {
          p_hMem = v22;
LABEL_25:
          GlobalFree(p_hMem);
        }
LABEL_26:
        v22 = &hMem;
        v23 = 1;
      }
    }
  }
  if ( v20 > 1 )
    GlobalFree(lpFilename);
  lpFilename = (LPWSTR)&v21;
  v20 = 1;
LABEL_30:
  if ( v17 > 1 )
    GlobalFree(v16);
  v17 = 1;
  v16 = &v18;
  if ( v26 > 1 )
    GlobalFree(v25);
  return 0x8000;
}

```

## disassembly

```asm
0x140008300  push    rbx
0x140008302  push    rsi
0x140008303  push    rdi
0x140008304  push    r14
0x140008306  push    r15
0x140008308  sub     rsp, 110h
0x14000830f  mov     rax, cs:__security_cookie
0x140008316  xor     rax, rsp
0x140008319  mov     [rsp+138h+var_38], rax
0x140008321  mov     ebx, 1
0x140008326  mov     [rsp+138h+var_90], ebx
0x14000832d  lea     rax, [rsp+138h+var_88]
0x140008335  mov     [rsp+138h+var_98], rax
0x14000833d  mov     [rsp+138h+var_D8], ebx
0x140008341  lea     rax, [rsp+138h+var_D0]
0x140008346  mov     [rsp+138h+var_E0], rax
0x14000834b  mov     esi, 1388h
0x140008350  mov     edx, esi
0x140008352  lea     rcx, [rsp+138h+var_98]
0x14000835a  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x14000835f  xor     edi, edi
0x140008361  test    al, al
0x140008363  jz      loc_140008608
0x140008369  mov     edx, esi
0x14000836b  lea     rcx, [rsp+138h+var_E0]
0x140008370  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x140008375  test    al, al
0x140008377  jz      loc_140008608
0x14000837d  mov     word ptr [rsp+138h+var_118], di
0x140008382  mov     r9d, [rsp+138h+var_90]
0x14000838a  mov     r8, [rsp+138h+var_98]
0x140008392  lea     edx, [rbx+9]
0x140008395  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140008399  call    cs:__imp_MsiLoadStringW
0x14000839f  mov     r14d, eax
0x1400083a2  mov     [rsp+138h+var_F8], eax
0x1400083a6  mov     [rsp+138h+var_C0], ebx
0x1400083aa  lea     rax, [rsp+138h+var_B8]
0x1400083b2  mov     [rsp+138h+lpFilename], rax
0x1400083b7  mov     esi, 104h
0x1400083bc  mov     edx, esi
0x1400083be  lea     rcx, [rsp+138h+lpFilename]
0x1400083c3  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x1400083c8  test    al, al
0x1400083ca  jz      loc_1400085E6
0x1400083d0  mov     r8d, esi; nSize
0x1400083d3  mov     rdx, [rsp+138h+lpFilename]; lpFilename
0x1400083d8  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x1400083df  call    cs:__imp_GetModuleFileNameW
0x1400083e5  test    eax, eax
0x1400083e7  jz      loc_1400085E6
0x1400083ed  mov     rax, [rsp+138h+lpFilename]
0x1400083f2  mov     [rax+206h], di
0x1400083f9  mov     [rsp+138h+var_F4], edi
0x1400083fd  lea     rdx, [rsp+138h+var_F4]
0x140008402  mov     rcx, [rsp+138h+lpFilename]
0x140008407  mov     rax, cs:?GetFileVersionInfoSizeW@VERSION@@3P6AKPEBGPEAK@ZEA; ulong (*VERSION::GetFileVersionInfoSizeW)(ushort const *,ulong *)
0x14000840e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008413  mov     esi, eax
0x140008415  mov     [rsp+138h+var_F0], eax
0x140008419  jmp     short loc_14000842F
0x14000841b  xor     esi, esi
0x14000841d  mov     [rsp+138h+var_F0], esi
0x140008421  mov     [rsp+138h+var_F4], esi
0x140008425  lea     ebx, [rsi+1]
0x140008428  xor     edi, edi
0x14000842a  mov     r14d, [rsp+138h+var_F8]
0x14000842f  test    esi, esi
0x140008431  jz      loc_1400085E6
0x140008437  mov     eax, ebx
0x140008439  mov     [rsp+138h+var_A8], ebx
0x140008440  lea     rcx, [rsp+138h+hMem]; hMem
0x140008448  mov     [rsp+138h+var_B0], rcx
0x140008450  cmp     esi, ebx
0x140008452  jle     short loc_140008476
0x140008454  movsxd  rdx, esi; dwBytes
0x140008457  mov     ecx, 40h ; '@'; uFlags
0x14000845c  call    cs:__imp_GlobalAlloc
0x140008462  mov     r15, rax
0x140008465  mov     eax, [rsp+138h+var_A8]
0x14000846c  mov     rcx, [rsp+138h+var_B0]
0x140008474  jmp     short loc_14000847E
0x140008476  lea     r15, [rsp+138h+hMem]
0x14000847e  test    r15, r15
0x140008481  jz      loc_1400085C5
0x140008487  lea     rax, [rsp+138h+hMem]
0x14000848f  cmp     rcx, rax
0x140008492  jz      short loc_14000849A
0x140008494  call    cs:__imp_GlobalFree
0x14000849a  mov     [rsp+138h+var_B0], r15
0x1400084a2  mov     [rsp+138h+var_A8], esi
0x1400084a9  mov     r9, r15
0x1400084ac  mov     r8d, esi
0x1400084af  mov     edx, [rsp+138h+var_F4]
0x1400084b3  mov     rcx, [rsp+138h+lpFilename]
0x1400084b8  mov     rax, cs:?GetFileVersionInfoW@VERSION@@3P6AHPEBGKKPEAX@ZEA; int (*VERSION::GetFileVersionInfoW)(ushort const *,ulong,ulong,void *)
0x1400084bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400084c4  test    eax, eax
0x1400084c6  jz      short loc_140008528
0x1400084c8  mov     [rsp+138h+var_F8], edi
0x1400084cc  mov     [rsp+138h+var_E8], rdi
0x1400084d1  lea     r9, [rsp+138h+var_F8]
0x1400084d6  lea     r8, [rsp+138h+var_E8]
0x1400084db  lea     rdx, asc_14000B818; "\\"
0x1400084e2  mov     rcx, [rsp+138h+var_B0]
0x1400084ea  mov     rax, cs:?VerQueryValueW@VERSION@@3P6AHQEAXPEBGPEAPEAXPEAI@ZEA; int (*VERSION::VerQueryValueW)(void * const,ushort const *,void * *,uint *)
0x1400084f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400084f6  test    eax, eax
0x1400084f8  jz      short loc_14000850E
0x1400084fa  cmp     [rsp+138h+var_F8], edi
0x1400084fe  jbe     short loc_14000850E
0x140008500  mov     rax, [rsp+138h+var_E8]
0x140008505  mov     r9d, [rax+8]
0x140008509  mov     edx, [rax+0Ch]
0x14000850c  jmp     short loc_14000852D
0x14000850e  cmp     [rsp+138h+var_A8], ebx
0x140008515  jle     loc_1400085CF
0x14000851b  mov     rcx, [rsp+138h+var_B0]
0x140008523  jmp     loc_1400085C9
0x140008528  mov     r9d, edi
0x14000852b  mov     edx, edi
0x14000852d  movzx   ecx, dx
0x140008530  shr     edx, 10h
0x140008533  movzx   eax, r9w
0x140008537  shr     r9d, 10h
0x14000853b  mov     [rsp+138h+var_108], ecx
0x14000853f  mov     [rsp+138h+var_110], edx
0x140008543  mov     dword ptr [rsp+138h+var_118], eax
0x140008547  lea     r8, aDD4dD; "%d.%d.%.4d.%d"
0x14000854e  mov     edx, 20h ; ' '; unsigned __int64
0x140008553  lea     rcx, [rsp+138h+var_78]; unsigned __int16 *
0x14000855b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140008560  test    eax, eax
0x140008562  js      short loc_14000850E
0x140008564  movsxd  rdx, [rsp+138h+var_D8]; unsigned __int64
0x140008569  lea     r9, [rsp+138h+var_78]
0x140008571  mov     r8, [rsp+138h+var_98]; unsigned __int16 *
0x140008579  mov     rcx, [rsp+138h+var_E0]; unsigned __int16 *
0x14000857e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140008583  cmp     r14d, 4E8h
0x14000858a  jz      short loc_14000859A
0x14000858c  mov     eax, 69h ; 'i'
0x140008591  cmp     r14d, 4E7h
0x140008598  jnz     short loc_14000859F
0x14000859a  mov     eax, 78h ; 'x'
0x14000859f  mov     [rsp+138h+var_108], eax
0x1400085a3  mov     word ptr [rsp+138h+var_110], di
0x1400085a8  mov     dword ptr [rsp+138h+var_118], r14d
0x1400085ad  xor     r9d, r9d
0x1400085b0  xor     r8d, r8d
0x1400085b3  mov     rdx, [rsp+138h+var_E0]
0x1400085b8  xor     ecx, ecx
0x1400085ba  call    cs:__imp_MsiMessageBoxExW
0x1400085c0  jmp     loc_14000850E
0x1400085c5  cmp     eax, ebx
0x1400085c7  jle     short loc_1400085CF
0x1400085c9  call    cs:__imp_GlobalFree
0x1400085cf  lea     rax, [rsp+138h+hMem]
0x1400085d7  mov     [rsp+138h+var_B0], rax
0x1400085df  mov     [rsp+138h+var_A8], ebx
0x1400085e6  cmp     [rsp+138h+var_C0], ebx
0x1400085ea  jle     short loc_1400085F7
0x1400085ec  mov     rcx, [rsp+138h+lpFilename]; hMem
0x1400085f1  call    cs:__imp_GlobalFree
0x1400085f7  lea     rax, [rsp+138h+var_B8]
0x1400085ff  mov     [rsp+138h+lpFilename], rax
0x140008604  mov     [rsp+138h+var_C0], ebx
0x140008608  cmp     [rsp+138h+var_D8], ebx
0x14000860c  jle     short loc_140008619
0x14000860e  mov     rcx, [rsp+138h+var_E0]; hMem
0x140008613  call    cs:__imp_GlobalFree
0x140008619  lea     rax, [rsp+138h+var_D0]
0x14000861e  mov     [rsp+138h+var_D8], ebx
0x140008622  mov     [rsp+138h+var_E0], rax
0x140008627  cmp     [rsp+138h+var_90], ebx
0x14000862e  jle     short loc_14000863E
0x140008630  mov     rcx, [rsp+138h+var_98]; hMem
0x140008638  call    cs:__imp_GlobalFree
0x14000863e  mov     eax, 8000h
0x140008643  mov     rcx, [rsp+138h+var_38]
0x14000864b  xor     rcx, rsp; StackCookie
0x14000864e  call    __security_check_cookie
0x140008653  add     rsp, 110h
0x14000865a  pop     r15
0x14000865c  pop     r14
0x14000865e  pop     rdi
0x14000865f  pop     rsi
0x140008660  pop     rbx
0x140008661  retn
```
