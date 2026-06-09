# CDriverMap::AddService(ushort const *,ulong)

- ea: `0x1800438cc`
- end: `0x180043def`
- name: `?AddService@CDriverMap@@AEAAJPEBGK@Z`
- size: `1315`
- prototype: `__int64 __fastcall(CDriverMap *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task`

## callers

- `0x180043490`

## callees

- `0x180005e40`
- `0x180006270`
- `0x180006d02`
- `0x180007014`
- `0x18000fa50`
- `0x180038aec`
- `0x180038d1c`
- `0x18004255c`
- `0x1800438cc`
- `0x1800448b4`
- `0x180044afc`
- `0x180044bcc`
- `0x180046840`
- `0x180046a00`
- `0x18006041c`
- `0x180066c10`

## string_xrefs

- `0x180043953`: `Service name lookup failed.`
- `0x180043966`: `CDriverMap::AddService`
- `0x18004398e`: `CDriverMap::AddService`
- `0x180043a3b`: `CDriverMap::AddService`
- `0x180043a64`: `CDriverMap::AddService`
- `0x180043b0e`: `CDriverMap::AddService`
- `0x180043b3d`: `CDriverMap::AddService`
- `0x180043c0f`: `CDriverMap::AddService`
- `0x180043c33`: `CDriverMap::AddService`
- `0x180043a29`: `0x%08x GetDriverPathFromServiceName failed for (%ws)`
- `0x180043b01`: `0x%08x Failed to query service start type for [%ws]`
- `0x180043b60`: `0x%08x Failed to query service start type for [%ws]`
- `0x180043b91`: `0x%08x Failed to query service start type for [%ws]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDriverMap::AddService(CDriverMap *this, const unsigned __int16 *a2, char a3)
{
  int DriverPathFromServiceName; // edi
  FILE *v7; // rax
  FILE *v8; // rax
  FILE *v9; // rax
  FILE *v10; // rax
  unsigned __int16 *v11; // rbx
  FILE *v12; // rax
  FILE *v13; // rax
  unsigned int v14; // ebx
  int IsServiceBootStart; // eax
  unsigned int v16; // edi
  FILE *v17; // rax
  FILE *v18; // rax
  FILE *v19; // rax
  const WCHAR *p_Src; // rdx
  __int128 *v21; // rax
  FILE *v22; // rax
  __int128 *v23; // rbx
  FILE *v24; // rax
  FILE *v25; // rax
  __int128 *v26; // r8
  struct CDriver *v27; // r15
  __int64 v28; // rbx
  char *v29; // r12
  int v30; // esi
  __int64 inserted; // rcx
  __int64 v32; // rax
  __int64 *v33; // rax
  FILE *v35; // rax
  FILE *v36; // rax
  FILE *v37; // rax
  unsigned __int16 *v38; // [rsp+30h] [rbp-A8h] BYREF
  int v39[2]; // [rsp+38h] [rbp-A0h] BYREF
  struct CDriver *v40; // [rsp+40h] [rbp-98h] BYREF
  char *v41; // [rsp+50h] [rbp-88h] BYREF
  unsigned __int64 v42; // [rsp+58h] [rbp-80h]
  __int128 Src; // [rsp+60h] [rbp-78h] BYREF
  __int64 v44; // [rsp+70h] [rbp-68h]
  unsigned __int64 v45; // [rsp+78h] [rbp-60h]
  __int128 v46; // [rsp+80h] [rbp-58h] BYREF
  __int64 v47; // [rsp+90h] [rbp-48h]
  __int64 v48; // [rsp+98h] [rbp-40h]

  Src = 0;
  v44 = 0;
  v45 = 7;
  LOWORD(Src) = 0;
  v46 = 0;
  v47 = 0;
  v48 = 7;
  LOWORD(v46) = 0;
  v38 = 0;
  v40 = 0;
  v39[0] = 0;
  DriverPathFromServiceName = CDriverMap::LookupString(this, a2, (const unsigned __int16 **)&v38);
  if ( DriverPathFromServiceName < 0 )
  {
    AslLogCallPrintf(2, "CDriverMap::AddService", 1540, "Service name lookup failed.");
    if ( EnableDevInvStdErrLog )
    {
      v7 = o___acrt_iob_func_0(2u);
      fprintf(v7, "Error: %s, %u: ", "CDriverMap::AddService", 1540);
      v8 = o___acrt_iob_func_0(2u);
      fprintf(v8, "Service name lookup failed.");
      v9 = o___acrt_iob_func_0(2u);
      fprintf(v9, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "Service name lookup failed.");
    goto LABEL_46;
  }
  if ( CDriverMap::FindService(this, v38) )
  {
LABEL_7:
    DriverPathFromServiceName = 0;
    goto LABEL_46;
  }
  DriverPathFromServiceName = CDriverMap::GetDriverPathFromServiceName(v38, &Src);
  if ( DriverPathFromServiceName >= 0 )
  {
    v14 = (a3 & 3) != 0 ? 2 : 4;
    IsServiceBootStart = CDriverMap::IsServiceBootStart(this, a2, v39);
    v16 = IsServiceBootStart;
    if ( IsServiceBootStart >= 0 )
    {
      if ( v39[0] )
        v14 |= 0x100u;
    }
    else
    {
      AslLogCallPrintf(
        3,
        "CDriverMap::AddService",
        1579,
        "0x%08x Failed to query service start type for [%ws]",
        IsServiceBootStart,
        a2);
      if ( EnableDevInvStdErrLog )
      {
        v17 = o___acrt_iob_func_0(2u);
        fprintf(v17, "Info: %s, %u: ", "CDriverMap::AddService", 1579);
        v18 = o___acrt_iob_func_0(2u);
        fprintf(v18, "0x%08x Failed to query service start type for [%ws]", v16, a2);
        v19 = o___acrt_iob_func_0(2u);
        fprintf(v19, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x4000000, "0x%08x Failed to query service start type for [%ws]", v16, a2);
    }
    p_Src = (const WCHAR *)&Src;
    if ( v45 > 7 )
      p_Src = (const WCHAR *)Src;
    DriverPathFromServiceName = CDriverMap::AddDriver(this, p_Src, v38, v14, &v40);
    if ( DriverPathFromServiceName >= 0 )
    {
      v27 = v40;
      if ( v40 )
      {
        try
        {
          v28 = *((_QWORD *)this + 11);
          v29 = *(char **)(v28 + 8);
          v30 = 0;
          *(_QWORD *)v39 = 0;
          inserted = v28;
          v32 = (__int64)v29;
          while ( !*(_BYTE *)(v32 + 25) )
          {
            v29 = (char *)v32;
            if ( *(_QWORD *)(v32 + 32) >= (unsigned __int64)v38 )
            {
              v30 = 1;
              inserted = v32;
              v32 = *(_QWORD *)v32;
            }
            else
            {
              v30 = 0;
              v32 = *(_QWORD *)(v32 + 16);
            }
          }
          if ( *(_BYTE *)(inserted + 25) || (unsigned __int64)v38 < *(_QWORD *)(inserted + 32) )
          {
            if ( *((_QWORD *)this + 12) == 0x555555555555555LL )
              std::_Throw_tree_length_error();
            v41 = (char *)this + 88;
            v42 = 0;
            v33 = (__int64 *)operator new(0x30u);
            v33[4] = (__int64)v38;
            v33[5] = 0;
            *v33 = v28;
            v33[1] = v28;
            v33[2] = v28;
            *((_WORD *)v33 + 12) = 0;
            v41 = v29;
            v42 = __PAIR64__(v39[0], v30);
            inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,_MEDIA_DEVICE_INFO>>>::_Insert_node(
                         (char *)this + 88,
                         &v41,
                         v33);
          }
          *(_QWORD *)(inserted + 40) = v27;
        }
        catch ( std::bad_alloc )
        {
          AslLogCallPrintf(2, "CDriverMap::AddService", 1616, "Out of memory");
          if ( EnableDevInvStdErrLog )
          {
            v35 = o___acrt_iob_func_0(2u);
            fprintf(v35, "Error: %s, %u: ", "CDriverMap::AddService", 1616);
            v36 = o___acrt_iob_func_0(2u);
            fprintf(v36, "Out of memory");
            v37 = o___acrt_iob_func_0(2u);
            fprintf(v37, "\n");
          }
          if ( g_DeviceMapLogFunction )
            TraceMessageCallback(0x2000000, "Out of memory");
          v39[0] = -2147024888;
          DriverPathFromServiceName = -2147024888;
          goto LABEL_46;
        }
        CDriverMap::GetDriverInfFromServiceName();
      }
      goto LABEL_7;
    }
    v21 = &Src;
    if ( v45 > 7 )
      v21 = (__int128 *)Src;
    AslLogCallPrintf(2, "CDriverMap::AddService", 1594, "Failed to add driver [%ws]", v21);
    if ( EnableDevInvStdErrLog )
    {
      v22 = o___acrt_iob_func_0(2u);
      fprintf(v22, "Warning: %s, %u: ", "CDriverMap::AddService", 1594);
      v23 = &Src;
      if ( v45 > 7 )
        v23 = (__int128 *)Src;
      v24 = o___acrt_iob_func_0(2u);
      fprintf(v24, "Failed to add driver [%ws]", v23);
      v25 = o___acrt_iob_func_0(2u);
      fprintf(v25, "\n");
    }
    if ( g_DeviceMapLogFunction )
    {
      v26 = &Src;
      if ( v45 > 7 )
        v26 = (__int128 *)Src;
      TraceMessageCallback(50331648, "Failed to add driver [%ws]", v26);
    }
  }
  else
  {
    AslLogCallPrintf(
      2,
      "CDriverMap::AddService",
      1560,
      "0x%08x GetDriverPathFromServiceName failed for (%ws)",
      DriverPathFromServiceName,
      v38);
    if ( EnableDevInvStdErrLog )
    {
      v10 = o___acrt_iob_func_0(2u);
      fprintf(v10, "Warning: %s, %u: ", "CDriverMap::AddService", 1560);
      v11 = v38;
      v12 = o___acrt_iob_func_0(2u);
      fprintf(v12, "0x%08x GetDriverPathFromServiceName failed for (%ws)", (unsigned int)DriverPathFromServiceName, v11);
      v13 = o___acrt_iob_func_0(2u);
      fprintf(v13, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(
        50331648,
        "0x%08x GetDriverPathFromServiceName failed for (%ws)",
        (unsigned int)DriverPathFromServiceName,
        v38);
  }
LABEL_46:
  std::wstring::~wstring(&v46);
  std::wstring::~wstring(&Src);
  return (unsigned int)DriverPathFromServiceName;
}

```

## disassembly

```asm
0x1800438cc  mov     r11, rsp
0x1800438cf  mov     [r11+18h], rbx
0x1800438d3  mov     [r11+20h], rsi
0x1800438d7  push    rdi
0x1800438d8  push    r12
0x1800438da  push    r13
0x1800438dc  push    r14
0x1800438de  push    r15
0x1800438e0  sub     rsp, 0B0h
0x1800438e7  mov     rax, cs:__security_cookie
0x1800438ee  xor     rax, rsp
0x1800438f1  mov     [rsp+0D8h+var_38], rax
0x1800438f9  mov     ebx, r8d
0x1800438fc  mov     r15, rdx
0x1800438ff  mov     r14, rcx
0x180043902  xorps   xmm0, xmm0
0x180043905  movups  [rsp+0D8h+Src], xmm0
0x18004390a  xor     r13d, r13d
0x18004390d  mov     [r11-68h], r13
0x180043911  lea     r12d, [r13+7]
0x180043915  mov     [r11-60h], r12
0x180043919  mov     [r11-78h], r13w
0x18004391e  movups  xmmword ptr [r11-58h], xmm0
0x180043923  mov     [r11-48h], r13
0x180043927  mov     [r11-40h], r12
0x18004392b  mov     [r11-58h], r13w
0x180043930  mov     [rsp+0D8h+var_A8], r13
0x180043935  mov     [rsp+0D8h+var_98], r13
0x18004393a  mov     [rsp+0D8h+var_A0], r13d
0x18004393f  lea     r8, [rsp+0D8h+var_A8]; unsigned __int16 **
0x180043944  call    ?LookupString@CDriverMap@@QEAAJPEBGAEAPEBG@Z; CDriverMap::LookupString(ushort const *,ushort const * &)
0x180043949  mov     edi, eax
0x18004394b  test    eax, eax
0x18004394d  jns     loc_1800439E8
0x180043953  lea     rbx, aServiceNameLoo; "Service name lookup failed."
0x18004395a  mov     r9, rbx
0x18004395d  mov     r14d, 604h
0x180043963  mov     r8d, r14d
0x180043966  lea     rdx, aCdrivermapAdds; "CDriverMap::AddService"
0x18004396d  lea     esi, [r13+2]
0x180043971  mov     ecx, esi
0x180043973  call    AslLogCallPrintf
0x180043978  cmp     cs:EnableDevInvStdErrLog, r13d
0x18004397f  jz      short loc_1800439C9
0x180043981  mov     ecx, esi; Ix
0x180043983  call    _o___acrt_iob_func_0
0x180043988  mov     rcx, rax; Stream
0x18004398b  mov     r9d, r14d
0x18004398e  lea     r8, aCdrivermapAdds; "CDriverMap::AddService"
0x180043995  lea     rdx, Format; "Error: %s, %u: "
0x18004399c  call    fprintf
0x1800439a1  mov     ecx, esi; Ix
0x1800439a3  call    _o___acrt_iob_func_0
0x1800439a8  mov     rcx, rax; Stream
0x1800439ab  mov     rdx, rbx; Format
0x1800439ae  call    fprintf
0x1800439b3  mov     ecx, esi; Ix
0x1800439b5  call    _o___acrt_iob_func_0
0x1800439ba  mov     rcx, rax; Stream
0x1800439bd  lea     rdx, asc_18011EAD8; "\n"
0x1800439c4  call    fprintf
0x1800439c9  cmp     cs:g_DeviceMapLogFunction, r13
0x1800439d0  jz      loc_180043DA1
0x1800439d6  mov     rdx, rbx
0x1800439d9  mov     ecx, 2000000h
0x1800439de  call    TraceMessageCallback
0x1800439e3  jmp     loc_180043DA1
0x1800439e8  mov     rdx, [rsp+0D8h+var_A8]; unsigned __int16 *
0x1800439ed  mov     rcx, r14; this
0x1800439f0  call    ?FindService@CDriverMap@@QEAAPEAVCDriver@@PEBG@Z; CDriverMap::FindService(ushort const *)
0x1800439f5  test    rax, rax
0x1800439f8  jz      short loc_180043A02
0x1800439fa  mov     edi, r13d
0x1800439fd  jmp     loc_180043DA1
0x180043a02  lea     rdx, [rsp+0D8h+Src]; Src
0x180043a07  mov     rcx, [rsp+0D8h+var_A8]; void *
0x180043a0c  call    ?GetDriverPathFromServiceName@CDriverMap@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CDriverMap::GetDriverPathFromServiceName(ushort const *,std::wstring &)
0x180043a11  mov     edi, eax
0x180043a13  test    eax, eax
0x180043a15  jns     loc_180043AD1
0x180043a1b  mov     rax, [rsp+0D8h+var_A8]
0x180043a20  mov     [rsp+0D8h+var_B0], rax
0x180043a25  mov     dword ptr [rsp+0D8h+var_B8], edi
0x180043a29  lea     r14, a0x08xGetdriver; "0x%08x GetDriverPathFromServiceName fai"...
0x180043a30  mov     r9, r14
0x180043a33  mov     ebx, 618h
0x180043a38  mov     r8d, ebx
0x180043a3b  lea     rdx, aCdrivermapAdds; "CDriverMap::AddService"
0x180043a42  mov     esi, 2
0x180043a47  mov     ecx, esi
0x180043a49  call    AslLogCallPrintf
0x180043a4e  cmp     cs:EnableDevInvStdErrLog, r13d
0x180043a55  jz      short loc_180043AAA
0x180043a57  mov     ecx, esi; Ix
0x180043a59  call    _o___acrt_iob_func_0
0x180043a5e  mov     rcx, rax; Stream
0x180043a61  mov     r9d, ebx
0x180043a64  lea     r8, aCdrivermapAdds; "CDriverMap::AddService"
0x180043a6b  lea     rdx, aWarningSU; "Warning: %s, %u: "
0x180043a72  call    fprintf
0x180043a77  mov     rbx, [rsp+0D8h+var_A8]
0x180043a7c  mov     ecx, esi; Ix
0x180043a7e  call    _o___acrt_iob_func_0
0x180043a83  mov     r9, rbx
0x180043a86  mov     r8d, edi
0x180043a89  mov     rdx, r14; Format
0x180043a8c  mov     rcx, rax; Stream
0x180043a8f  call    fprintf
0x180043a94  mov     ecx, esi; Ix
0x180043a96  call    _o___acrt_iob_func_0
0x180043a9b  mov     rcx, rax; Stream
0x180043a9e  lea     rdx, asc_18011EAD8; "\n"
0x180043aa5  call    fprintf
0x180043aaa  cmp     cs:g_DeviceMapLogFunction, r13
0x180043ab1  jz      loc_180043DA1
0x180043ab7  mov     r9, [rsp+0D8h+var_A8]
0x180043abc  mov     r8d, edi
0x180043abf  mov     rdx, r14
0x180043ac2  mov     ecx, 3000000h
0x180043ac7  call    TraceMessageCallback
0x180043acc  jmp     loc_180043DA1
0x180043ad1  and     bl, 3
0x180043ad4  neg     bl
0x180043ad6  sbb     ebx, ebx
0x180043ad8  and     ebx, 0FFFFFFFEh
0x180043adb  add     ebx, 4
0x180043ade  lea     r8, [rsp+0D8h+var_A0]; int *
0x180043ae3  mov     rdx, r15; unsigned __int16 *
0x180043ae6  mov     rcx, r14; this
0x180043ae9  call    ?IsServiceBootStart@CDriverMap@@AEAAJPEBGAEAH@Z; CDriverMap::IsServiceBootStart(ushort const *,int &)
0x180043aee  mov     edi, eax
0x180043af0  test    eax, eax
0x180043af2  jns     loc_180043BA4
0x180043af8  mov     [rsp+0D8h+var_B0], r15
0x180043afd  mov     dword ptr [rsp+0D8h+var_B8], eax
0x180043b01  lea     r9, a0x08xFailedToQ; "0x%08x Failed to query service start ty"...
0x180043b08  mov     r8d, 62Bh
0x180043b0e  lea     rdx, aCdrivermapAdds; "CDriverMap::AddService"
0x180043b15  mov     ecx, 3
0x180043b1a  call    AslLogCallPrintf
0x180043b1f  mov     esi, 2
0x180043b24  cmp     cs:EnableDevInvStdErrLog, r13d
0x180043b2b  jz      short loc_180043B82
0x180043b2d  mov     ecx, esi; Ix
0x180043b2f  call    _o___acrt_iob_func_0
0x180043b34  mov     rcx, rax; Stream
0x180043b37  mov     r9d, 62Bh
0x180043b3d  lea     r8, aCdrivermapAdds; "CDriverMap::AddService"
0x180043b44  lea     rdx, aInfoSU; "Info: %s, %u: "
0x180043b4b  call    fprintf
0x180043b50  mov     ecx, esi; Ix
0x180043b52  call    _o___acrt_iob_func_0
0x180043b57  mov     rcx, rax; Stream
0x180043b5a  mov     r9, r15
0x180043b5d  mov     r8d, edi
0x180043b60  lea     rdx, a0x08xFailedToQ; "0x%08x Failed to query service start ty"...
0x180043b67  call    fprintf
0x180043b6c  mov     ecx, esi; Ix
0x180043b6e  call    _o___acrt_iob_func_0
0x180043b73  mov     rcx, rax; Stream
0x180043b76  lea     rdx, asc_18011EAD8; "\n"
0x180043b7d  call    fprintf
0x180043b82  cmp     cs:g_DeviceMapLogFunction, r13
0x180043b89  jz      short loc_180043BB4
0x180043b8b  mov     r9, r15
0x180043b8e  mov     r8d, edi
0x180043b91  lea     rdx, a0x08xFailedToQ; "0x%08x Failed to query service start ty"...
0x180043b98  mov     ecx, 4000000h
0x180043b9d  call    TraceMessageCallback
0x180043ba2  jmp     short loc_180043BB4
0x180043ba4  mov     esi, 2
0x180043ba9  cmp     [rsp+0D8h+var_A0], r13d
0x180043bae  jz      short loc_180043BB4
0x180043bb0  bts     ebx, 8
0x180043bb4  lea     rdx, [rsp+0D8h+Src]
0x180043bb9  cmp     [rsp+0D8h+var_60], r12
0x180043bbe  cmova   rdx, qword ptr [rsp+0D8h+Src]; lpSrc
0x180043bc4  lea     rax, [rsp+0D8h+var_98]
0x180043bc9  mov     [rsp+0D8h+var_B8], rax; struct CDriver **
0x180043bce  mov     r9d, ebx; unsigned int
0x180043bd1  mov     r8, [rsp+0D8h+var_A8]; unsigned __int16 *
0x180043bd6  mov     rcx, r14; this
0x180043bd9  call    ?AddDriver@CDriverMap@@AEAAJPEBG0KPEAPEAVCDriver@@@Z; CDriverMap::AddDriver(ushort const *,ushort const *,ulong,CDriver * *)
0x180043bde  mov     edi, eax
0x180043be0  test    eax, eax
0x180043be2  jns     loc_180043CB0
0x180043be8  lea     rax, [rsp+0D8h+Src]
0x180043bed  cmp     [rsp+0D8h+var_60], r12
0x180043bf2  cmova   rax, qword ptr [rsp+0D8h+Src]
0x180043bf8  mov     [rsp+0D8h+var_B8], rax
0x180043bfd  lea     r14, aFailedToAddDri_0; "Failed to add driver [%ws]"
0x180043c04  mov     r9, r14
0x180043c07  mov     ebx, 63Ah
0x180043c0c  mov     r8d, ebx
0x180043c0f  lea     rdx, aCdrivermapAdds; "CDriverMap::AddService"
0x180043c16  mov     ecx, esi
0x180043c18  call    AslLogCallPrintf
0x180043c1d  cmp     cs:EnableDevInvStdErrLog, r13d
0x180043c24  jz      short loc_180043C81
0x180043c26  mov     ecx, esi; Ix
0x180043c28  call    _o___acrt_iob_func_0
0x180043c2d  mov     rcx, rax; Stream
0x180043c30  mov     r9d, ebx
0x180043c33  lea     r8, aCdrivermapAdds; "CDriverMap::AddService"
0x180043c3a  lea     rdx, aWarningSU; "Warning: %s, %u: "
0x180043c41  call    fprintf
0x180043c46  lea     rbx, [rsp+0D8h+Src]
0x180043c4b  cmp     [rsp+0D8h+var_60], r12
0x180043c50  cmova   rbx, qword ptr [rsp+0D8h+Src]
0x180043c56  mov     ecx, esi; Ix
0x180043c58  call    _o___acrt_iob_func_0
0x180043c5d  mov     r8, rbx
0x180043c60  mov     rdx, r14; Format
0x180043c63  mov     rcx, rax; Stream
0x180043c66  call    fprintf
0x180043c6b  mov     ecx, esi; Ix
0x180043c6d  call    _o___acrt_iob_func_0
0x180043c72  mov     rcx, rax; Stream
0x180043c75  lea     rdx, asc_18011EAD8; "\n"
0x180043c7c  call    fprintf
0x180043c81  cmp     cs:g_DeviceMapLogFunction, r13
0x180043c88  jz      loc_180043DA1
0x180043c8e  lea     r8, [rsp+0D8h+Src]
0x180043c93  cmp     [rsp+0D8h+var_60], r12
0x180043c98  cmova   r8, qword ptr [rsp+0D8h+Src]
0x180043c9e  mov     rdx, r14
0x180043ca1  mov     ecx, 3000000h
0x180043ca6  call    TraceMessageCallback
0x180043cab  jmp     loc_180043DA1
0x180043cb0  mov     r15, [rsp+0D8h+var_98]
0x180043cb5  test    r15, r15
0x180043cb8  jz      loc_1800439FA
0x180043cbe  lea     rdi, [r14+58h]
0x180043cc2  mov     rbx, [rdi]
0x180043cc5  mov     r12, [rbx+8]
0x180043cc9  mov     esi, r13d
0x180043ccc  xor     eax, eax
0x180043cce  mov     qword ptr [rsp+0D8h+var_A0], rax
0x180043cd3  mov     rcx, rbx
0x180043cd6  mov     rax, r12
0x180043cd9  mov     rdx, [rsp+0D8h+var_A8]
0x180043cde  cmp     [r12+19h], r13b
0x180043ce3  jnz     short loc_180043D08
0x180043ce5  mov     r12, rax
0x180043ce8  cmp     [rax+20h], rdx
0x180043cec  jnb     short loc_180043CF7
0x180043cee  mov     esi, r13d
0x180043cf1  mov     rax, [rax+10h]
0x180043cf5  jmp     short loc_180043D02
0x180043cf7  mov     esi, 1
0x180043cfc  mov     rcx, rax
0x180043cff  mov     rax, [rax]
0x180043d02  cmp     [rax+19h], r13b
0x180043d06  jz      short loc_180043CE5
0x180043d08  cmp     [rcx+19h], r13b
0x180043d0c  jnz     short loc_180043D14
0x180043d0e  cmp     rdx, [rcx+20h]
0x180043d12  jnb     short loc_180043D7F
0x180043d14  mov     rax, 555555555555555h
0x180043d1e  cmp     [rdi+8], rax
0x180043d22  jz      loc_180043DE8
0x180043d28  mov     [rsp+0D8h+var_88], rdi
0x180043d2d  mov     [rsp+0D8h+var_80], r13
0x180043d32  mov     ecx, 30h ; '0'; Size
0x180043d37  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180043d3c  nop
0x180043d3d  mov     rcx, [rsp+0D8h+var_A8]
0x180043d42  mov     [rax+20h], rcx
0x180043d46  mov     [rax+28h], r13
0x180043d4a  mov     [rax], rbx
0x180043d4d  mov     [rax+8], rbx
0x180043d51  mov     [rax+10h], rbx
0x180043d55  mov     [rax+18h], r13w
0x180043d5a  mov     [rsp+0D8h+var_88], r12
0x180043d5f  mov     dword ptr [rsp+0D8h+var_80], esi
0x180043d63  mov     rcx, qword ptr [rsp+0D8h+var_A0]
0x180043d68  mov     dword ptr [rsp+0D8h+var_80+4], ecx
0x180043d6c  mov     r8, rax
0x180043d6f  lea     rdx, [rsp+0D8h+var_88]
0x180043d74  mov     rcx, rdi
0x180043d77  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_MEDIA_DEVICE_INFO@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_MEDIA_DEVICE_INFO@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_MEDIA_DEVICE_INFO@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,_MEDIA_DEVICE_INFO>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,_MEDIA_DEVICE_INFO>,void *> *>,std::_Tree_node<std::pair<std::wstring const,_MEDIA_DEVICE_INFO>,void *> * const)
0x180043d7c  mov     rcx, rax
0x180043d7f  mov     [rcx+28h], r15
0x180043d83  lea     r8, [rsp+0D8h+var_58]
0x180043d8b  mov     rdx, [rsp+0D8h+var_A8]
0x180043d90  mov     rcx, r14
0x180043d93  call    ?GetDriverInfFromServiceName@CDriverMap@@QEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CDriverMap::GetDriverInfFromServiceName(ushort const *,std::wstring &)
0x180043d98  jmp     loc_1800439FA
0x180043d9d  mov     edi, [rsp+0D8h+var_A0]
0x180043da1  lea     rcx, [rsp+0D8h+var_58]; void *
0x180043da9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043dae  nop
0x180043daf  lea     rcx, [rsp+0D8h+Src]; void *
0x180043db4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043db9  mov     eax, edi
0x180043dbb  mov     rcx, [rsp+0D8h+var_38]
0x180043dc3  xor     rcx, rsp; StackCookie
0x180043dc6  call    __security_check_cookie
0x180043dcb  lea     r11, [rsp+0D8h+var_28]
0x180043dd3  mov     rbx, [r11+40h]
  ... truncated ...
```
