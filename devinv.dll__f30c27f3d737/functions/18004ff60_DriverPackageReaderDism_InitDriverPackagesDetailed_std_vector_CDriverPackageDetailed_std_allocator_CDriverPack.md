# DriverPackageReaderDism::InitDriverPackagesDetailed(std::vector<CDriverPackageDetailed *,std::allocator<CDriverPackageDetailed *>> &)

- ea: `0x18004ff60`
- end: `0x18005045d`
- name: `?InitDriverPackagesDetailed@DriverPackageReaderDism@@UEAAJAEAV?$vector@PEAVCDriverPackageDetailed@@V?$allocator@PEAVCDriverPackageDetailed@@@std@@@std@@@Z`
- size: `1277`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180005e40`
- `0x1800066f0`
- `0x180006d02`
- `0x180007014`
- `0x180018934`
- `0x18004d314`
- `0x18004eb8c`
- `0x18004eed0`
- `0x18004ff60`
- `0x18006041c`
- `0x180066c10`
- `0x180116010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005015b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005015b`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18005016b`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180050183`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18005016b`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180050183`

## string_xrefs

- `0x18004ffb8`: `DriverPackageReaderDism::InitDriverPackagesDetailed`
- `0x18004ffdf`: `DriverPackageReaderDism::InitDriverPackagesDetailed`
- `0x18005020a`: `DriverPackageReaderDism::InitDriverPackagesDetailed`
- `0x18005022d`: `DriverPackageReaderDism::InitDriverPackagesDetailed`
- `0x1800502b9`: `DriverPackageReaderDism::InitDriverPackagesDetailed`
- `0x1800502df`: `DriverPackageReaderDism::InitDriverPackagesDetailed`
- `0x180050386`: `DriverPackageReaderDism::InitDriverPackagesDetailed`
- `0x1800503ac`: `DriverPackageReaderDism::InitDriverPackagesDetailed`
- `0x180050087`: `DriverPackageReaderDism::IsPackageInTelecommand`
- `0x1800500ad`: `DriverPackageReaderDism::IsPackageInTelecommand`
- `0x180050127`: `DriverPackageReaderDism::IsPackageInTelecommand`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DriverPackageReaderDism::InitDriverPackagesDetailed(DriverPackageReaderDism *a1, __int64 a2)
{
  DriverPackageReaderDism *v3; // r15
  FILE *v4; // rax
  FILE *v5; // rax
  FILE *v6; // rax
  int v8; // esi
  __int64 i; // rax
  FILE *v10; // rax
  FILE *v11; // rax
  FILE *v12; // rax
  __int64 v13; // r14
  wchar_t *v14; // rax
  wchar_t *v15; // rax
  wchar_t *v16; // r8
  char *v17; // rax
  signed __int64 v18; // r8
  int v19; // ecx
  int v20; // edx
  struct _DismDriverPackage *v21; // rsi
  CDriverPackageDetailed *v22; // rax
  DriverPackageReaderDism *v23; // rcx
  struct CDriverPackageDetailed *v24; // r14
  FILE *v25; // rax
  FILE *v26; // rax
  FILE *v27; // rax
  int v28; // eax
  int v29; // r14d
  FILE *v30; // rax
  FILE *v31; // rax
  FILE *v32; // rax
  int inited; // eax
  FILE *v34; // rax
  FILE *v35; // rax
  FILE *v36; // rax
  struct CDriverPackageDetailed **v37; // rdx
  FILE *v38; // rax
  FILE *v39; // rax
  FILE *v40; // rax
  int v41; // [rsp+30h] [rbp-278h]
  unsigned int v42; // [rsp+34h] [rbp-274h] BYREF
  struct _DismDriverPackage *v43; // [rsp+38h] [rbp-270h] BYREF
  struct CDriverPackageDetailed *v44; // [rsp+40h] [rbp-268h] BYREF
  DriverPackageReaderDism *v45; // [rsp+48h] [rbp-260h]
  CDriverPackageDetailed *v46; // [rsp+50h] [rbp-258h]
  wchar_t Str[264]; // [rsp+60h] [rbp-248h] BYREF

  v3 = a1;
  v45 = a1;
  v43 = 0;
  v42 = 0;
  if ( *((_DWORD *)a1 + 5) )
  {
    v8 = DriverPackageReaderDism::EnumDismDrivers(a1, &v43, &v42);
    if ( v8 >= 0 )
    {
      for ( i = 0; ; i = (unsigned int)(v41 + 1) )
      {
        v41 = i;
        if ( (unsigned int)i >= v42 )
          break;
        if ( *((_QWORD *)v3 + 1) )
        {
          v13 = 100 * i;
          _o_wcscpy_s(Str, 260, *(_QWORD *)((char *)v43 + 100 * i + 8));
          v14 = wcsrchr(Str, 0x5Cu);
          if ( v14 )
          {
            *v14 = 0;
            v15 = wcsrchr(Str, 0x5Cu);
            if ( v15 )
            {
              v16 = v15 + 1;
              v17 = (char *)(*((_QWORD *)v3 + 1) + 240LL);
              v18 = (char *)v16 - v17;
              do
              {
                v19 = *(unsigned __int16 *)&v17[v18];
                v20 = *(unsigned __int16 *)v17 - v19;
                if ( v20 )
                  break;
                v17 += 2;
              }
              while ( v19 );
              if ( !v20 )
              {
                v21 = (struct _DismDriverPackage *)((char *)v43 + v13);
                v22 = (CDriverPackageDetailed *)operator new(0x268u, (const struct std::nothrow_t *)std::nothrow);
                v46 = v22;
                if ( v22 )
                  v24 = CDriverPackageDetailed::CDriverPackageDetailed(v22);
                else
                  v24 = 0;
                v44 = v24;
                if ( !v24 )
                {
                  AslLogCallPrintf(2, "DriverPackageReaderDism::InitDriverPackagesDetailed", 231, "Out of memory");
                  if ( EnableDevInvStdErrLog )
                  {
                    v25 = o___acrt_iob_func_0(2u);
                    fprintf(v25, "Error: %s, %u: ", "DriverPackageReaderDism::InitDriverPackagesDetailed", 231);
                    v26 = o___acrt_iob_func_0(2u);
                    fprintf(v26, "Out of memory");
                    v27 = o___acrt_iob_func_0(2u);
                    fprintf(v27, "\n");
                  }
                  if ( g_DeviceMapLogFunction )
                    TraceMessageCallback(0x2000000, "Out of memory");
                  v8 = -2147024888;
                  break;
                }
                inited = DriverPackageReaderDism::InitDriverPackageDetailedItem(v23, v21, v24);
                v8 = inited;
                if ( inited >= 0 )
                {
                  try
                  {
                    v37 = *(struct CDriverPackageDetailed ***)(a2 + 8);
                    if ( v37 == *(struct CDriverPackageDetailed ***)(a2 + 16) )
                    {
                      std::vector<CDevice *>::_Emplace_reallocate<CDevice * const &>(a2, v37, &v44);
                    }
                    else
                    {
                      *v37 = v24;
                      *(_QWORD *)(a2 + 8) += 8LL;
                    }
                  }
                  catch ( std::bad_alloc )
                  {
                    AslLogCallPrintf(2, "DriverPackageReaderDism::InitDriverPackagesDetailed", 250, "Out of memory");
                    if ( EnableDevInvStdErrLog )
                    {
                      v38 = o___acrt_iob_func_0(2u);
                      fprintf(v38, "Error: %s, %u: ", "DriverPackageReaderDism::InitDriverPackagesDetailed", 250);
                      v39 = o___acrt_iob_func_0(2u);
                      fprintf(v39, "Out of memory");
                      v40 = o___acrt_iob_func_0(2u);
                      fprintf(v40, "\n");
                    }
                    if ( g_DeviceMapLogFunction )
                      TraceMessageCallback(0x2000000, "Out of memory");
                    v8 = -2147024888;
                    v3 = v45;
                    break;
                  }
                }
                else
                {
                  AslLogCallPrintf(
                    2,
                    "DriverPackageReaderDism::InitDriverPackagesDetailed",
                    239,
                    "Failed to init detailed driver package %08x",
                    inited);
                  if ( EnableDevInvStdErrLog )
                  {
                    v34 = o___acrt_iob_func_0(2u);
                    fprintf(v34, "Error: %s, %u: ", "DriverPackageReaderDism::InitDriverPackagesDetailed", 239);
                    v35 = o___acrt_iob_func_0(2u);
                    fprintf(v35, "Failed to init detailed driver package %08x", v8);
                    v36 = o___acrt_iob_func_0(2u);
                    fprintf(v36, "\n");
                  }
                  if ( g_DeviceMapLogFunction )
                    TraceMessageCallback(0x2000000, "Failed to init detailed driver package %08x", v8);
                  (**(void (__fastcall ***)(struct CDriverPackageDetailed *, __int64))v24)(v24, 1);
                }
              }
            }
          }
        }
        else
        {
          AslLogCallPrintf(
            2,
            "DriverPackageReaderDism::IsPackageInTelecommand",
            755,
            "m_DriverMap is NULL [%#x]",
            -2147467259);
          if ( EnableDevInvStdErrLog )
          {
            v10 = o___acrt_iob_func_0(2u);
            fprintf(v10, "Error: %s, %u: ", "DriverPackageReaderDism::IsPackageInTelecommand", 755);
            v11 = o___acrt_iob_func_0(2u);
            fprintf(v11, "m_DriverMap is NULL [%#x]", -2147467259);
            v12 = o___acrt_iob_func_0(2u);
            fprintf(v12, "\n");
          }
          if ( g_DeviceMapLogFunction )
            TraceMessageCallback(0x2000000, "m_DriverMap is NULL [%#x]", -2147467259);
          AslLogCallPrintf(
            1,
            "DriverPackageReaderDism::IsPackageInTelecommand",
            755,
            "m_DriverMap is NULL [%#x]",
            -2147467259);
        }
      }
    }
    if ( v43 )
    {
      v28 = (*((__int64 (**)(void))v3 + 8))();
      v29 = v28;
      if ( v28 < 0 )
      {
        AslLogCallPrintf(2, "DriverPackageReaderDism::InitDriverPackagesDetailed", 260, "Failed with %08x", v28);
        if ( EnableDevInvStdErrLog )
        {
          v30 = o___acrt_iob_func_0(2u);
          fprintf(v30, "Error: %s, %u: ", "DriverPackageReaderDism::InitDriverPackagesDetailed", 260);
          v31 = o___acrt_iob_func_0(2u);
          fprintf(v31, "Failed with %08x", v29);
          v32 = o___acrt_iob_func_0(2u);
          fprintf(v32, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "Failed with %08x", v29);
      }
    }
    return (unsigned int)v8;
  }
  else
  {
    AslLogCallPrintf(3, "DriverPackageReaderDism::InitDriverPackagesDetailed", 206, "Dism isn't initialized");
    if ( EnableDevInvStdErrLog )
    {
      v4 = o___acrt_iob_func_0(2u);
      fprintf(v4, "Info: %s, %u: ", "DriverPackageReaderDism::InitDriverPackagesDetailed", 206);
      v5 = o___acrt_iob_func_0(2u);
      fprintf(v5, "Dism isn't initialized");
      v6 = o___acrt_iob_func_0(2u);
      fprintf(v6, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x4000000, "Dism isn't initialized");
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x18004ff60  mov     [rsp+arg_10], rbx
0x18004ff65  push    rsi
0x18004ff66  push    rdi
0x18004ff67  push    r13
0x18004ff69  push    r14
0x18004ff6b  push    r15
0x18004ff6d  sub     rsp, 280h
0x18004ff74  mov     rax, cs:__security_cookie
0x18004ff7b  xor     rax, rsp
0x18004ff7e  mov     [rsp+2A8h+var_38], rax
0x18004ff86  mov     r13, rdx
0x18004ff89  mov     r15, rcx
0x18004ff8c  mov     [rsp+2A8h+var_260], rcx
0x18004ff91  xor     ebx, ebx
0x18004ff93  mov     [rsp+2A8h+var_270], rbx
0x18004ff98  mov     [rsp+2A8h+var_274], ebx
0x18004ff9c  cmp     [rcx+14h], ebx
0x18004ff9f  jnz     loc_18005003A
0x18004ffa5  lea     rsi, aDismIsnTInitia; "Dism isn't initialized"
0x18004ffac  mov     r9, rsi
0x18004ffaf  mov     r14d, 0CEh
0x18004ffb5  mov     r8d, r14d
0x18004ffb8  lea     rdx, aDriverpackager_7; "DriverPackageReaderDism::InitDriverPack"...
0x18004ffbf  lea     ecx, [rbx+3]
0x18004ffc2  call    AslLogCallPrintf
0x18004ffc7  cmp     cs:EnableDevInvStdErrLog, ebx
0x18004ffcd  jz      short loc_18005001A
0x18004ffcf  lea     edi, [rbx+2]
0x18004ffd2  mov     ecx, edi; Ix
0x18004ffd4  call    _o___acrt_iob_func_0
0x18004ffd9  mov     rcx, rax; Stream
0x18004ffdc  mov     r9d, r14d
0x18004ffdf  lea     r8, aDriverpackager_7; "DriverPackageReaderDism::InitDriverPack"...
0x18004ffe6  lea     rdx, aInfoSU; "Info: %s, %u: "
0x18004ffed  call    fprintf
0x18004fff2  mov     ecx, edi; Ix
0x18004fff4  call    _o___acrt_iob_func_0
0x18004fff9  mov     rcx, rax; Stream
0x18004fffc  mov     rdx, rsi; Format
0x18004ffff  call    fprintf
0x180050004  mov     ecx, edi; Ix
0x180050006  call    _o___acrt_iob_func_0
0x18005000b  mov     rcx, rax; Stream
0x18005000e  lea     rdx, asc_18011EAD8; "\n"
0x180050015  call    fprintf
0x18005001a  cmp     cs:g_DeviceMapLogFunction, rbx
0x180050021  jz      short loc_180050030
0x180050023  mov     rdx, rsi
0x180050026  mov     ecx, 4000000h
0x18005002b  call    TraceMessageCallback
0x180050030  mov     eax, 80004005h
0x180050035  jmp     loc_180050338
0x18005003a  lea     r8, [rsp+2A8h+var_274]; unsigned int *
0x18005003f  lea     rdx, [rsp+2A8h+var_270]; struct _DismDriverPackage **
0x180050044  call    ?EnumDismDrivers@DriverPackageReaderDism@@QEAAJPEAPEAU_DismDriverPackage@@AEAI@Z; DriverPackageReaderDism::EnumDismDrivers(_DismDriverPackage * *,uint &)
0x180050049  mov     esi, eax
0x18005004b  mov     edi, 2
0x180050050  test    eax, eax
0x180050052  js      loc_180050283
0x180050058  mov     eax, ebx
0x18005005a  mov     [rsp+2A8h+var_278], eax
0x18005005e  cmp     eax, [rsp+2A8h+var_274]
0x180050062  jnb     loc_180050283
0x180050068  cmp     [r15+8], rbx
0x18005006c  jnz     loc_180050143
0x180050072  mov     [rsp+2A8h+var_288], 80004005h
0x18005007a  lea     r9, aMDrivermapIsNu; "m_DriverMap is NULL [%#x]"
0x180050081  mov     r8d, 2F3h
0x180050087  lea     rdx, aDriverpackager_14; "DriverPackageReaderDism::IsPackageInTel"...
0x18005008e  mov     ecx, edi
0x180050090  call    AslLogCallPrintf
0x180050095  cmp     cs:EnableDevInvStdErrLog, ebx
0x18005009b  jz      short loc_1800500F2
0x18005009d  mov     ecx, edi; Ix
0x18005009f  call    _o___acrt_iob_func_0
0x1800500a4  mov     rcx, rax; Stream
0x1800500a7  mov     r9d, 2F3h
0x1800500ad  lea     r8, aDriverpackager_14; "DriverPackageReaderDism::IsPackageInTel"...
0x1800500b4  lea     rdx, Format; "Error: %s, %u: "
0x1800500bb  call    fprintf
0x1800500c0  mov     ecx, edi; Ix
0x1800500c2  call    _o___acrt_iob_func_0
0x1800500c7  mov     rcx, rax; Stream
0x1800500ca  mov     r8d, 80004005h
0x1800500d0  lea     rdx, aMDrivermapIsNu; "m_DriverMap is NULL [%#x]"
0x1800500d7  call    fprintf
0x1800500dc  mov     ecx, edi; Ix
0x1800500de  call    _o___acrt_iob_func_0
0x1800500e3  mov     rcx, rax; Stream
0x1800500e6  lea     rdx, asc_18011EAD8; "\n"
0x1800500ed  call    fprintf
0x1800500f2  cmp     cs:g_DeviceMapLogFunction, rbx
0x1800500f9  jz      short loc_180050112
0x1800500fb  mov     r8d, 80004005h
0x180050101  lea     rdx, aMDrivermapIsNu; "m_DriverMap is NULL [%#x]"
0x180050108  mov     ecx, 2000000h
0x18005010d  call    TraceMessageCallback
0x180050112  mov     [rsp+2A8h+var_288], 80004005h
0x18005011a  lea     r9, aMDrivermapIsNu; "m_DriverMap is NULL [%#x]"
0x180050121  mov     r8d, 2F3h
0x180050127  lea     rdx, aDriverpackager_14; "DriverPackageReaderDism::IsPackageInTel"...
0x18005012e  mov     ecx, 1
0x180050133  call    AslLogCallPrintf
0x180050138  mov     eax, [rsp+2A8h+var_278]
0x18005013c  inc     eax
0x18005013e  jmp     loc_18005005A
0x180050143  imul    r14, rax, 64h ; 'd'
0x180050147  mov     r8, [rsp+2A8h+var_270]
0x18005014c  mov     r8, [r14+r8+8]
0x180050151  mov     edx, 104h
0x180050156  lea     rcx, [rsp+2A8h+Str]
0x18005015b  call    cs:__imp__o_wcscpy_s
0x180050161  mov     edx, 5Ch ; '\'; Ch
0x180050166  lea     rcx, [rsp+2A8h+Str]; Str
0x18005016b  call    cs:__imp_wcsrchr
0x180050171  test    rax, rax
0x180050174  jz      short loc_180050138
0x180050176  mov     [rax], bx
0x180050179  mov     edx, 5Ch ; '\'; Ch
0x18005017e  lea     rcx, [rsp+2A8h+Str]; Str
0x180050183  call    cs:__imp_wcsrchr
0x180050189  test    rax, rax
0x18005018c  jz      short loc_180050138
0x18005018e  lea     r8, [rax+2]
0x180050192  mov     rax, [r15+8]
0x180050196  add     rax, 0F0h
0x18005019c  sub     r8, rax
0x18005019f  movzx   edx, word ptr [rax]
0x1800501a2  movzx   ecx, word ptr [rax+r8]
0x1800501a7  sub     edx, ecx
0x1800501a9  jnz     short loc_1800501B2
0x1800501ab  add     rax, rdi
0x1800501ae  test    ecx, ecx
0x1800501b0  jnz     short loc_18005019F
0x1800501b2  test    edx, edx
0x1800501b4  jnz     short loc_180050138
0x1800501b6  mov     rsi, [rsp+2A8h+var_270]
0x1800501bb  add     rsi, r14
0x1800501be  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800501c5  mov     ecx, 268h; unsigned __int64
0x1800501ca  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800501cf  mov     [rsp+2A8h+var_258], rax
0x1800501d4  test    rax, rax
0x1800501d7  jz      short loc_1800501E6
0x1800501d9  mov     rcx, rax; this
0x1800501dc  call    ??0CDriverPackageDetailed@@QEAA@XZ; CDriverPackageDetailed::CDriverPackageDetailed(void)
0x1800501e1  mov     r14, rax
0x1800501e4  jmp     short loc_1800501E9
0x1800501e6  mov     r14, rbx
0x1800501e9  mov     [rsp+2A8h+var_268], r14
0x1800501ee  test    r14, r14
0x1800501f1  jnz     loc_180050360
0x1800501f7  lea     rsi, aOutOfMemory_0; "Out of memory"
0x1800501fe  mov     r9, rsi
0x180050201  mov     r14d, 0E7h
0x180050207  mov     r8d, r14d
0x18005020a  lea     rdx, aDriverpackager_7; "DriverPackageReaderDism::InitDriverPack"...
0x180050211  mov     ecx, edi
0x180050213  call    AslLogCallPrintf
0x180050218  cmp     cs:EnableDevInvStdErrLog, ebx
0x18005021e  jz      short loc_180050268
0x180050220  mov     ecx, edi; Ix
0x180050222  call    _o___acrt_iob_func_0
0x180050227  mov     rcx, rax; Stream
0x18005022a  mov     r9d, r14d
0x18005022d  lea     r8, aDriverpackager_7; "DriverPackageReaderDism::InitDriverPack"...
0x180050234  lea     rdx, Format; "Error: %s, %u: "
0x18005023b  call    fprintf
0x180050240  mov     ecx, edi; Ix
0x180050242  call    _o___acrt_iob_func_0
0x180050247  mov     rcx, rax; Stream
0x18005024a  mov     rdx, rsi; Format
0x18005024d  call    fprintf
0x180050252  mov     ecx, edi; Ix
0x180050254  call    _o___acrt_iob_func_0
0x180050259  mov     rcx, rax; Stream
0x18005025c  lea     rdx, asc_18011EAD8; "\n"
0x180050263  call    fprintf
0x180050268  cmp     cs:g_DeviceMapLogFunction, rbx
0x18005026f  jz      short loc_18005027E
0x180050271  mov     rdx, rsi
0x180050274  mov     ecx, 2000000h
0x180050279  call    TraceMessageCallback
0x18005027e  mov     esi, 80070008h
0x180050283  mov     rcx, [rsp+2A8h+var_270]
0x180050288  test    rcx, rcx
0x18005028b  jz      loc_180050336
0x180050291  mov     rax, [r15+40h]
0x180050295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005029a  mov     r14d, eax
0x18005029d  test    eax, eax
0x18005029f  jns     loc_180050336
0x1800502a5  mov     [rsp+2A8h+var_288], eax
0x1800502a9  lea     r15, aFailedWith08x; "Failed with %08x"
0x1800502b0  mov     r9, r15
0x1800502b3  mov     r8d, 104h
0x1800502b9  lea     rdx, aDriverpackager_7; "DriverPackageReaderDism::InitDriverPack"...
0x1800502c0  mov     ecx, edi
0x1800502c2  call    AslLogCallPrintf
0x1800502c7  cmp     cs:EnableDevInvStdErrLog, ebx
0x1800502cd  jz      short loc_18005031D
0x1800502cf  mov     ecx, edi; Ix
0x1800502d1  call    _o___acrt_iob_func_0
0x1800502d6  mov     rcx, rax; Stream
0x1800502d9  mov     r9d, 104h
0x1800502df  lea     r8, aDriverpackager_7; "DriverPackageReaderDism::InitDriverPack"...
0x1800502e6  lea     rdx, Format; "Error: %s, %u: "
0x1800502ed  call    fprintf
0x1800502f2  mov     ecx, edi; Ix
0x1800502f4  call    _o___acrt_iob_func_0
0x1800502f9  mov     rcx, rax; Stream
0x1800502fc  mov     r8d, r14d
0x1800502ff  mov     rdx, r15; Format
0x180050302  call    fprintf
0x180050307  mov     ecx, edi; Ix
0x180050309  call    _o___acrt_iob_func_0
0x18005030e  mov     rcx, rax; Stream
0x180050311  lea     rdx, asc_18011EAD8; "\n"
0x180050318  call    fprintf
0x18005031d  cmp     cs:g_DeviceMapLogFunction, rbx
0x180050324  jz      short loc_180050336
0x180050326  mov     r8d, r14d
0x180050329  mov     rdx, r15
0x18005032c  mov     ecx, 2000000h
0x180050331  call    TraceMessageCallback
0x180050336  mov     eax, esi
0x180050338  mov     rcx, [rsp+2A8h+var_38]
0x180050340  xor     rcx, rsp; StackCookie
0x180050343  call    __security_check_cookie
0x180050348  mov     rbx, [rsp+2A8h+arg_10]
0x180050350  add     rsp, 280h
0x180050357  pop     r15
0x180050359  pop     r14
0x18005035b  pop     r13
0x18005035d  pop     rdi
0x18005035e  pop     rsi
0x18005035f  retn
0x180050360  mov     r8, r14; struct CDriverPackageDetailed *
0x180050363  mov     rdx, rsi; struct _DismDriverPackage *
0x180050366  call    ?InitDriverPackageDetailedItem@DriverPackageReaderDism@@QEAAJAEAU_DismDriverPackage@@AEAVCDriverPackageDetailed@@@Z; DriverPackageReaderDism::InitDriverPackageDetailedItem(_DismDriverPackage &,CDriverPackageDetailed &)
0x18005036b  mov     esi, eax
0x18005036d  test    eax, eax
0x18005036f  jns     loc_180050423
0x180050375  mov     [rsp+2A8h+var_288], eax
0x180050379  lea     r9, aFailedToInitDe_0; "Failed to init detailed driver package "...
0x180050380  mov     r8d, 0EFh
0x180050386  lea     rdx, aDriverpackager_7; "DriverPackageReaderDism::InitDriverPack"...
0x18005038d  mov     ecx, edi
0x18005038f  call    AslLogCallPrintf
0x180050394  cmp     cs:EnableDevInvStdErrLog, ebx
0x18005039a  jz      short loc_1800503EE
0x18005039c  mov     ecx, edi; Ix
0x18005039e  call    _o___acrt_iob_func_0
0x1800503a3  mov     rcx, rax; Stream
0x1800503a6  mov     r9d, 0EFh
0x1800503ac  lea     r8, aDriverpackager_7; "DriverPackageReaderDism::InitDriverPack"...
0x1800503b3  lea     rdx, Format; "Error: %s, %u: "
0x1800503ba  call    fprintf
0x1800503bf  mov     ecx, edi; Ix
0x1800503c1  call    _o___acrt_iob_func_0
0x1800503c6  mov     rcx, rax; Stream
0x1800503c9  mov     r8d, esi
0x1800503cc  lea     rdx, aFailedToInitDe_0; "Failed to init detailed driver package "...
0x1800503d3  call    fprintf
0x1800503d8  mov     ecx, edi; Ix
0x1800503da  call    _o___acrt_iob_func_0
0x1800503df  mov     rcx, rax; Stream
0x1800503e2  lea     rdx, asc_18011EAD8; "\n"
0x1800503e9  call    fprintf
0x1800503ee  cmp     cs:g_DeviceMapLogFunction, rbx
0x1800503f5  jz      short loc_18005040B
0x1800503f7  mov     r8d, esi
0x1800503fa  lea     rdx, aFailedToInitDe_0; "Failed to init detailed driver package "...
0x180050401  mov     ecx, 2000000h
0x180050406  call    TraceMessageCallback
0x18005040b  mov     rax, [r14]
0x18005040e  mov     edx, 1
0x180050413  mov     rcx, r14
0x180050416  mov     rax, [rax]
0x180050419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005041e  jmp     loc_180050138
0x180050423  mov     rdx, [r13+8]
0x180050427  cmp     rdx, [r13+10h]
0x18005042b  jz      short loc_180050437
0x18005042d  mov     [rdx], r14
0x180050430  add     qword ptr [r13+8], 8
0x180050435  jmp     short loc_180050445
0x180050437  lea     r8, [rsp+2A8h+var_268]
0x18005043c  mov     rcx, r13
0x18005043f  call    ??$_Emplace_reallocate@AEBQEAVCDevice@@@?$vector@PEAVCDevice@@V?$allocator@PEAVCDevice@@@std@@@std@@AEAAPEAPEAVCDevice@@QEAPEAV2@AEBQEAV2@@Z; std::vector<CDevice *>::_Emplace_reallocate<CDevice * const &>(CDevice * * const,CDevice * const &)
0x180050444  nop
0x180050445  jmp     loc_180050138
0x18005044a  xor     ebx, ebx
0x18005044c  lea     edi, [rbx+2]
0x18005044f  mov     esi, [rsp+2A8h+var_278]
0x180050453  mov     r15, [rsp+2A8h+var_260]
0x180050458  jmp     loc_180050283
```
