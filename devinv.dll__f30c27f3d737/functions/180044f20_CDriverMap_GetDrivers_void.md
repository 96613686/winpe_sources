# CDriverMap::GetDrivers(void)

- ea: `0x180044f20`
- end: `0x180045ab9`
- name: `?GetDrivers@CDriverMap@@QEAAJXZ`
- size: `2969`
- prototype: `__int64 __fastcall(CDriverMap *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x180023180`

## callees

- `0x180006d02`
- `0x180007014`
- `0x180032a00`
- `0x180032c14`
- `0x180036c58`
- `0x180042c30`
- `0x180042d10`
- `0x180043490`
- `0x180043f54`
- `0x180044f20`
- `0x180045ac0`
- `0x180048300`
- `0x180057608`
- `0x18006041c`
- `0x180066c10`

## string_xrefs

- `0x18004572f`: `Telcache is not initialized [%#x]`
- `0x180044ff8`: `TelCacheProvider::BatchBegin failed with [%#x]`
- `0x180045053`: `TelCacheProvider::BatchBegin failed with [%#x]`
- `0x180045524`: `TelCacheProvider::BatchEnd failed with [%#x]`
- `0x180045571`: `TelCacheProvider::BatchEnd failed with [%#x]`
- `0x18004559f`: `TelCacheProvider::BatchEnd failed with [%#x]`
- `0x1800455ae`: `TelCacheProvider::BatchEnd failed with [%#x]`
- `0x180045812`: `TelCacheProvider::BatchEnd failed with [%#x]`
- `0x18004585f`: `TelCacheProvider::BatchEnd failed with [%#x]`
- `0x18004588d`: `TelCacheProvider::BatchEnd failed with [%#x]`
- `0x18004589c`: `TelCacheProvider::BatchEnd failed with [%#x]`
- `0x1800455eb`: `TelCacheProvider::GetItemCount failed [%#x]`
- `0x180045635`: `TelCacheProvider::GetItemCount failed [%#x]`
- `0x180045663`: `TelCacheProvider::GetItemCount failed [%#x]`
- `0x180045676`: `TelCacheProvider::GetItemCount failed [%#x]`
- `0x1800458d9`: `TelCacheProvider::GetItemCount failed [%#x]`
- `0x180045923`: `TelCacheProvider::GetItemCount failed [%#x]`
- `0x180045951`: `TelCacheProvider::GetItemCount failed [%#x]`
- `0x180045960`: `TelCacheProvider::GetItemCount failed [%#x]`
- `0x18004511d`: `[0x%08x] Failed to initialize inventory cache`
- `0x18004568f`: `TelCache driverBinary count after scan is %d`
- `0x1800456e2`: `TelCache driverBinary count after scan is %d`
- `0x180045719`: `TelCache driverBinary count after scan is %d`
- `0x180045988`: `TelCache driverPackage count after scan is %d`

## pseudocode

```c
__int64 __fastcall CDriverMap::GetDrivers(CDriverMap *this)
{
  FILE *v2; // rax
  FILE *v3; // rax
  FILE *v4; // rax
  int v5; // eax
  unsigned int v6; // edi
  const char *v7; // rbx
  __int64 v8; // r15
  _DWORD *v9; // rbx
  int v10; // eax
  const char *v11; // rbx
  FILE *v12; // rax
  FILE *v13; // rax
  FILE *v14; // rax
  __int64 v15; // r8
  const char *v16; // r9
  struct CInventoryCache *v17; // rax
  FILE *v18; // rax
  FILE *v19; // rax
  FILE *v20; // rax
  int v21; // eax
  FILE *v22; // rax
  FILE *v23; // rax
  FILE *v24; // rax
  FILE *v25; // rax
  FILE *v26; // rax
  FILE *v27; // rax
  int v28; // eax
  FILE *v29; // rax
  FILE *v30; // rax
  FILE *v31; // rax
  int v32; // eax
  int v33; // ebx
  FILE *v34; // rax
  FILE *v35; // rax
  FILE *v36; // rax
  __int64 v37; // rcx
  unsigned int v38; // ebx
  __int64 v39; // rdx
  struct CDevice *v40; // rdx
  int v41; // eax
  int v42; // ebx
  FILE *v43; // rax
  FILE *v44; // rax
  FILE *v45; // rax
  int v46; // eax
  int v47; // ebx
  FILE *v48; // rax
  FILE *v49; // rax
  FILE *v50; // rax
  FILE *v51; // rax
  unsigned int v52; // ebx
  FILE *v53; // rax
  FILE *v54; // rax
  FILE *v55; // rax
  FILE *v56; // rax
  FILE *v57; // rax
  int v58; // eax
  int v59; // ebx
  FILE *v60; // rax
  FILE *v61; // rax
  FILE *v62; // rax
  int ItemCount; // eax
  int v64; // ebx
  FILE *v65; // rax
  FILE *v66; // rax
  FILE *v67; // rax
  FILE *v68; // rax
  unsigned int v69; // ebx
  FILE *v70; // rax
  FILE *v71; // rax
  FILE *v72; // rax
  FILE *v73; // rax
  FILE *v74; // rax
  __int64 v76; // [rsp+20h] [rbp-58h]
  __int64 v77; // [rsp+20h] [rbp-58h]
  __int64 v78; // [rsp+20h] [rbp-58h]
  unsigned int v79; // [rsp+88h] [rbp+10h] BYREF

  v79 = 0;
  if ( !qword_180157238 || !qword_1801572C8 )
  {
    v7 = "Telcache is not initialized [%#x]";
    v8 = 371;
    v6 = -2147467259;
    AslLogCallPrintf(2, "CDriverMap::GetDrivers", 371, "Telcache is not initialized [%#x]", -2147467259);
    goto LABEL_76;
  }
  AslLogCallPrintf(3, "CDriverMap::GetDrivers", 394, "Begin CDriverMap::GetDrivers");
  if ( EnableDevInvStdErrLog )
  {
    v2 = o___acrt_iob_func_0(2u);
    fprintf(v2, "Info: %s, %u: ", "CDriverMap::GetDrivers", 394);
    v3 = o___acrt_iob_func_0(2u);
    fprintf(v3, "Begin CDriverMap::GetDrivers");
    v4 = o___acrt_iob_func_0(2u);
    fprintf(v4, "\n");
  }
  if ( g_DeviceMapLogFunction )
    TraceMessageCallback(0x4000000, "Begin CDriverMap::GetDrivers");
  v5 = TelCacheProvider::BatchBegin((TelCacheProvider *)g_DriverBinaryStore);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = "TelCacheProvider::BatchBegin failed with [%#x]";
    v8 = 399;
    AslLogCallPrintf(2, "CDriverMap::GetDrivers", 399, "TelCacheProvider::BatchBegin failed with [%#x]", v5);
LABEL_76:
    if ( EnableDevInvStdErrLog )
    {
      v55 = o___acrt_iob_func_0(2u);
      fprintf(v55, "Error: %s, %u: ", "CDriverMap::GetDrivers", v8);
      v56 = o___acrt_iob_func_0(2u);
      fprintf(v56, v7, v6);
      v57 = o___acrt_iob_func_0(2u);
      fprintf(v57, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, v7, v6);
    LODWORD(v76) = v6;
    AslLogCallPrintf(1, "CDriverMap::GetDrivers", v8, v7, v76);
LABEL_81:
    if ( *((_DWORD *)this + 48) )
    {
      v58 = TelCacheProvider::BatchEnd((TelCacheProvider *)g_DriverPackageStore);
      v59 = v58;
      if ( v58 < 0 )
      {
        AslLogCallPrintf(2, "CDriverMap::GetDrivers", 501, "TelCacheProvider::BatchEnd failed with [%#x]", v58);
        if ( EnableDevInvStdErrLog )
        {
          v60 = o___acrt_iob_func_0(2u);
          fprintf(v60, "Error: %s, %u: ", "CDriverMap::GetDrivers", 501);
          v61 = o___acrt_iob_func_0(2u);
          fprintf(v61, "TelCacheProvider::BatchEnd failed with [%#x]", v59);
          v62 = o___acrt_iob_func_0(2u);
          fprintf(v62, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "TelCacheProvider::BatchEnd failed with [%#x]", v59);
        AslLogCallPrintf(1, "CDriverMap::GetDrivers", 501, "TelCacheProvider::BatchEnd failed with [%#x]", v59);
      }
      ItemCount = TelCacheProvider::GetItemCount((TelCacheProvider *)g_DriverPackageStore, &v79);
      v64 = ItemCount;
      if ( ItemCount >= 0 )
      {
        AslLogCallPrintf(3, "CDriverMap::GetDrivers", 510, "TelCache driverPackage count after scan is %d", v79);
        if ( EnableDevInvStdErrLog )
        {
          v68 = o___acrt_iob_func_0(2u);
          fprintf(v68, "Info: %s, %u: ", "CDriverMap::GetDrivers", 510);
          v69 = v79;
          v70 = o___acrt_iob_func_0(2u);
          fprintf(v70, "TelCache driverPackage count after scan is %d", v69);
          v71 = o___acrt_iob_func_0(2u);
          fprintf(v71, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(1744830464, "TelCache driverPackage count after scan is %d", v79);
      }
      else
      {
        AslLogCallPrintf(2, "CDriverMap::GetDrivers", 506, "TelCacheProvider::GetItemCount failed [%#x]", ItemCount);
        if ( EnableDevInvStdErrLog )
        {
          v65 = o___acrt_iob_func_0(2u);
          fprintf(v65, "Error: %s, %u: ", "CDriverMap::GetDrivers", 506);
          v66 = o___acrt_iob_func_0(2u);
          fprintf(v66, "TelCacheProvider::GetItemCount failed [%#x]", v64);
          v67 = o___acrt_iob_func_0(2u);
          fprintf(v67, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "TelCacheProvider::GetItemCount failed [%#x]", v64);
        AslLogCallPrintf(1, "CDriverMap::GetDrivers", 506, "TelCacheProvider::GetItemCount failed [%#x]", v64);
      }
    }
    *((_QWORD *)this + 24) = 0;
    AslLogCallPrintf(3, "CDriverMap::GetDrivers", 517, "End CDriverMap::GetDrivers");
    if ( EnableDevInvStdErrLog )
    {
      v72 = o___acrt_iob_func_0(2u);
      fprintf(v72, "Info: %s, %u: ", "CDriverMap::GetDrivers", 517);
      v73 = o___acrt_iob_func_0(2u);
      fprintf(v73, "End CDriverMap::GetDrivers");
      v74 = o___acrt_iob_func_0(2u);
      fprintf(v74, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x4000000, "End CDriverMap::GetDrivers");
    return v6;
  }
  v9 = (_DWORD *)((char *)this + 192);
  if ( (*(_DWORD *)this & 0x100000) != 0 )
  {
    *((_DWORD *)this + 49) = 1;
  }
  else
  {
    *v9 = 1;
    v10 = TelCacheProvider::BatchBegin((TelCacheProvider *)g_DriverPackageStore);
    v6 = v10;
    if ( v10 < 0 )
    {
      v11 = "TelCacheProvider::BatchBegin failed with [%#x]";
      AslLogCallPrintf(2, "CDriverMap::GetDrivers", 411, "TelCacheProvider::BatchBegin failed with [%#x]", v10);
      if ( EnableDevInvStdErrLog )
      {
        v12 = o___acrt_iob_func_0(2u);
        fprintf(v12, "Error: %s, %u: ", "CDriverMap::GetDrivers", 411);
        v13 = o___acrt_iob_func_0(2u);
        fprintf(v13, "TelCacheProvider::BatchBegin failed with [%#x]", v6);
        v14 = o___acrt_iob_func_0(2u);
        fprintf(v14, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "TelCacheProvider::BatchBegin failed with [%#x]", v6);
      v15 = 411;
      goto LABEL_16;
    }
  }
  v17 = CInventoryCache::Load(*(_DWORD *)this);
  *((_QWORD *)this + 95) = v17;
  if ( v17 )
  {
    if ( !*v9 || (v21 = CDriverMap::AddDriverStorePackages(this, 0), v6 = v21, v21 >= 0) )
    {
      if ( !(unsigned int)CDriverMap::GetFilterDrivers(this) )
      {
        AslLogCallPrintf(2, "CDriverMap::GetDrivers", 441, "Failed to get filter drivers [%#x]", -2147467259);
        if ( EnableDevInvStdErrLog )
        {
          v25 = o___acrt_iob_func_0(2u);
          fprintf(v25, "Error: %s, %u: ", "CDriverMap::GetDrivers", 441);
          v26 = o___acrt_iob_func_0(2u);
          fprintf(v26, "Failed to get filter drivers [%#x]", -2147467259);
          v27 = o___acrt_iob_func_0(2u);
          fprintf(v27, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "Failed to get filter drivers [%#x]", -2147467259);
        AslLogCallPrintf(1, "CDriverMap::GetDrivers", 441, "Failed to get filter drivers [%#x]", -2147467259);
      }
      v28 = CDriverMap::AddScmDrivers(this);
      v6 = v28;
      if ( v28 >= 0 )
      {
        v32 = CDriverMap::AddUserDrivers(this);
        v6 = 0;
        v33 = v32;
        if ( v32 < 0 )
        {
          AslLogCallPrintf(2, "CDriverMap::GetDrivers", 459, "[0x%08x] Failed to add user mode drivers", v32);
          if ( EnableDevInvStdErrLog )
          {
            v34 = o___acrt_iob_func_0(2u);
            fprintf(v34, "Error: %s, %u: ", "CDriverMap::GetDrivers", 459);
            v35 = o___acrt_iob_func_0(2u);
            fprintf(v35, "[0x%08x] Failed to add user mode drivers", v33);
            v36 = o___acrt_iob_func_0(2u);
            fprintf(v36, "\n");
          }
          if ( g_DeviceMapLogFunction )
            TraceMessageCallback(0x2000000, "[0x%08x] Failed to add user mode drivers", v33);
          AslLogCallPrintf(1, "CDriverMap::GetDrivers", 459, "[0x%08x] Failed to add user mode drivers", v33);
        }
        if ( *((_DWORD *)this + 49) )
        {
          v37 = *((_QWORD *)this + 96);
          if ( v37 && (unsigned int)((__int64)(*(_QWORD *)(v37 + 32) - *(_QWORD *)(v37 + 24)) >> 3) )
          {
            v38 = 0;
            do
            {
              v39 = *(_QWORD *)(v37 + 24);
              if ( v38 < (unsigned __int64)((*(_QWORD *)(v37 + 32) - v39) >> 3) )
              {
                v40 = *(struct CDevice **)(v39 + 8LL * v38);
                if ( v40 )
                  CDriverMap::AddPackageToCache(this, v40);
              }
              v37 = *((_QWORD *)this + 96);
              ++v38;
            }
            while ( v38 < (unsigned int)((__int64)(*(_QWORD *)(v37 + 32) - *(_QWORD *)(v37 + 24)) >> 3) );
          }
          CDriverMap::RemoveDeletedDriverPackages(this);
        }
        goto LABEL_59;
      }
      AslLogCallPrintf(2, "CDriverMap::GetDrivers", 448, "[0x%08x] Failed to add SCM drivers", v28);
      if ( EnableDevInvStdErrLog )
      {
        v29 = o___acrt_iob_func_0(2u);
        fprintf(v29, "Error: %s, %u: ", "CDriverMap::GetDrivers", 448);
        v30 = o___acrt_iob_func_0(2u);
        fprintf(v30, "[0x%08x] Failed to add SCM drivers", v6);
        v31 = o___acrt_iob_func_0(2u);
        fprintf(v31, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "[0x%08x] Failed to add SCM drivers", v6);
      v16 = "[0x%08x] Failed to add SCM drivers";
      v15 = 448;
LABEL_17:
      LODWORD(v77) = v6;
      AslLogCallPrintf(1, "CDriverMap::GetDrivers", v15, v16, v77);
LABEL_59:
      v41 = TelCacheProvider::BatchEnd((TelCacheProvider *)g_DriverBinaryStore);
      v42 = v41;
      if ( v41 < 0 )
      {
        AslLogCallPrintf(2, "CDriverMap::GetDrivers", 483, "TelCacheProvider::BatchEnd failed with [%#x]", v41);
        if ( EnableDevInvStdErrLog )
        {
          v43 = o___acrt_iob_func_0(2u);
          fprintf(v43, "Error: %s, %u: ", "CDriverMap::GetDrivers", 483);
          v44 = o___acrt_iob_func_0(2u);
          fprintf(v44, "TelCacheProvider::BatchEnd failed with [%#x]", v42);
          v45 = o___acrt_iob_func_0(2u);
          fprintf(v45, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "TelCacheProvider::BatchEnd failed with [%#x]", v42);
        AslLogCallPrintf(1, "CDriverMap::GetDrivers", 483, "TelCacheProvider::BatchEnd failed with [%#x]", v42);
      }
      v46 = TelCacheProvider::GetItemCount((TelCacheProvider *)g_DriverBinaryStore, &v79);
      v47 = v46;
      if ( v46 >= 0 )
      {
        AslLogCallPrintf(3, "CDriverMap::GetDrivers", 492, "TelCache driverBinary count after scan is %d", v79);
        if ( EnableDevInvStdErrLog )
        {
          v51 = o___acrt_iob_func_0(2u);
          fprintf(v51, "Info: %s, %u: ", "CDriverMap::GetDrivers", 492);
          v52 = v79;
          v53 = o___acrt_iob_func_0(2u);
          fprintf(v53, "TelCache driverBinary count after scan is %d", v52);
          v54 = o___acrt_iob_func_0(2u);
          fprintf(v54, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(1744830464, "TelCache driverBinary count after scan is %d", v79);
      }
      else
      {
        AslLogCallPrintf(2, "CDriverMap::GetDrivers", 488, "TelCacheProvider::GetItemCount failed [%#x]", v46);
        if ( EnableDevInvStdErrLog )
        {
          v48 = o___acrt_iob_func_0(2u);
          fprintf(v48, "Error: %s, %u: ", "CDriverMap::GetDrivers", 488);
          v49 = o___acrt_iob_func_0(2u);
          fprintf(v49, "TelCacheProvider::GetItemCount failed [%#x]", v47);
          v50 = o___acrt_iob_func_0(2u);
          fprintf(v50, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "TelCacheProvider::GetItemCount failed [%#x]", v47);
        LODWORD(v78) = v47;
        AslLogCallPrintf(1, "CDriverMap::GetDrivers", 488, "TelCacheProvider::GetItemCount failed [%#x]", v78);
      }
      goto LABEL_81;
    }
    v11 = "[0x%08x] Failed to add driver store drivers";
    AslLogCallPrintf(2, "CDriverMap::GetDrivers", 434, "[0x%08x] Failed to add driver store drivers", v21);
    if ( EnableDevInvStdErrLog )
    {
      v22 = o___acrt_iob_func_0(2u);
      fprintf(v22, "Error: %s, %u: ", "CDriverMap::GetDrivers", 434);
      v23 = o___acrt_iob_func_0(2u);
      fprintf(v23, "[0x%08x] Failed to add driver store drivers", v6);
      v24 = o___acrt_iob_func_0(2u);
      fprintf(v24, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "[0x%08x] Failed to add driver store drivers", v6);
    v15 = 434;
LABEL_16:
    v16 = v11;
    goto LABEL_17;
  }
  v6 = -2147467259;
  AslLogCallPrintf(2, "CDriverMap::GetDrivers", 424, "[0x%08x] Failed to initialize inventory cache", -2147467259);
  if ( EnableDevInvStdErrLog )
  {
    v18 = o___acrt_iob_func_0(2u);
    fprintf(v18, "Error: %s, %u: ", "CDriverMap::GetDrivers", 424);
    v19 = o___acrt_iob_func_0(2u);
    fprintf(v19, "[0x%08x] Failed to initialize inventory cache", -2147467259);
    v20 = o___acrt_iob_func_0(2u);
    fprintf(v20, "\n");
  }
  if ( g_DeviceMapLogFunction )
    TraceMessageCallback(0x2000000, "[0x%08x] Failed to initialize inventory cache", -2147467259);
  AslLogCallPrintf(1, "CDriverMap::GetDrivers", 424, "[0x%08x] Failed to initialize inventory cache", -2147467259);
  return v6;
}

```

## disassembly

```asm
0x180044f20  mov     rax, rsp
0x180044f23  push    rbx
0x180044f24  push    rbp
0x180044f25  push    rsi
0x180044f26  push    rdi
0x180044f27  push    r12
0x180044f29  push    r13
0x180044f2b  push    r14
0x180044f2d  push    r15
0x180044f2f  sub     rsp, 38h
0x180044f33  xor     r14d, r14d
0x180044f36  mov     r12, rcx
0x180044f39  cmp     cs:qword_180157238, r14
0x180044f40  mov     [rax+10h], r14d
0x180044f44  jz      loc_18004572F
0x180044f4a  cmp     cs:qword_1801572C8, r14
0x180044f51  jz      loc_18004572F
0x180044f57  lea     rbx, aBeginCdriverma; "Begin CDriverMap::GetDrivers"
0x180044f5e  mov     edi, 18Ah
0x180044f63  lea     rsi, aCdrivermapGetd_2; "CDriverMap::GetDrivers"
0x180044f6a  mov     r9, rbx
0x180044f6d  mov     r8d, edi
0x180044f70  lea     ecx, [r14+3]
0x180044f74  mov     rdx, rsi
0x180044f77  call    AslLogCallPrintf
0x180044f7c  cmp     cs:EnableDevInvStdErrLog, r14d
0x180044f83  lea     ebp, [r14+2]
0x180044f87  lea     r13, asc_18011EAD8; "\n"
0x180044f8e  jz      short loc_180044FD0
0x180044f90  mov     ecx, ebp; Ix
0x180044f92  call    _o___acrt_iob_func_0
0x180044f97  mov     rcx, rax; Stream
0x180044f9a  lea     rdx, aInfoSU; "Info: %s, %u: "
0x180044fa1  mov     r9d, edi
0x180044fa4  mov     r8, rsi
0x180044fa7  call    fprintf
0x180044fac  mov     ecx, ebp; Ix
0x180044fae  call    _o___acrt_iob_func_0
0x180044fb3  mov     rcx, rax; Stream
0x180044fb6  mov     rdx, rbx; Format
0x180044fb9  call    fprintf
0x180044fbe  mov     ecx, ebp; Ix
0x180044fc0  call    _o___acrt_iob_func_0
0x180044fc5  mov     rcx, rax; Stream
0x180044fc8  mov     rdx, r13; Format
0x180044fcb  call    fprintf
0x180044fd0  cmp     cs:g_DeviceMapLogFunction, r14
0x180044fd7  jz      short loc_180044FE6
0x180044fd9  mov     rdx, rbx
0x180044fdc  mov     ecx, 4000000h
0x180044fe1  call    TraceMessageCallback
0x180044fe6  lea     rcx, ?g_DriverBinaryStore@@3VTelCacheProvider@@A; this
0x180044fed  call    ?BatchBegin@TelCacheProvider@@QEAAJXZ; TelCacheProvider::BatchBegin(void)
0x180044ff2  mov     edi, eax
0x180044ff4  test    eax, eax
0x180044ff6  jns     short loc_18004501E
0x180044ff8  lea     rbx, aTelcacheprovid_28; "TelCacheProvider::BatchBegin failed wit"...
0x180044fff  mov     dword ptr [rsp+78h+var_58], eax
0x180045003  mov     r15d, 18Fh
0x180045009  mov     r9, rbx
0x18004500c  mov     r8d, r15d
0x18004500f  mov     rdx, rsi
0x180045012  mov     ecx, ebp
0x180045014  call    AslLogCallPrintf
0x180045019  jmp     loc_180045768
0x18004501e  test    dword ptr [r12], 100000h
0x180045026  lea     rbx, [r12+0C0h]
0x18004502e  mov     r15d, 1
0x180045034  jnz     loc_1800450FB
0x18004503a  lea     rcx, ?g_DriverPackageStore@@3VTelCacheProvider@@A; this
0x180045041  mov     [rbx], r15d
0x180045044  call    ?BatchBegin@TelCacheProvider@@QEAAJXZ; TelCacheProvider::BatchBegin(void)
0x180045049  mov     edi, eax
0x18004504b  test    eax, eax
0x18004504d  jns     loc_180045103
0x180045053  lea     rbx, aTelcacheprovid_28; "TelCacheProvider::BatchBegin failed wit"...
0x18004505a  mov     dword ptr [rsp+78h+var_58], eax
0x18004505e  mov     r9, rbx
0x180045061  mov     r8d, 19Bh
0x180045067  mov     rdx, rsi
0x18004506a  mov     ecx, ebp
0x18004506c  call    AslLogCallPrintf
0x180045071  cmp     cs:EnableDevInvStdErrLog, r14d
0x180045078  jz      short loc_1800450C0
0x18004507a  mov     ecx, ebp; Ix
0x18004507c  call    _o___acrt_iob_func_0
0x180045081  mov     rcx, rax; Stream
0x180045084  lea     rdx, Format; "Error: %s, %u: "
0x18004508b  mov     r9d, 19Bh
0x180045091  mov     r8, rsi
0x180045094  call    fprintf
0x180045099  mov     ecx, ebp; Ix
0x18004509b  call    _o___acrt_iob_func_0
0x1800450a0  mov     rcx, rax; Stream
0x1800450a3  mov     r8d, edi
0x1800450a6  mov     rdx, rbx; Format
0x1800450a9  call    fprintf
0x1800450ae  mov     ecx, ebp; Ix
0x1800450b0  call    _o___acrt_iob_func_0
0x1800450b5  mov     rcx, rax; Stream
0x1800450b8  mov     rdx, r13; Format
0x1800450bb  call    fprintf
0x1800450c0  cmp     cs:g_DeviceMapLogFunction, 0
0x1800450c8  mov     r14d, 2000000h
0x1800450ce  jz      short loc_1800450DE
0x1800450d0  mov     r8d, edi
0x1800450d3  mov     rdx, rbx
0x1800450d6  mov     ecx, r14d
0x1800450d9  call    TraceMessageCallback
0x1800450de  mov     r8d, 19Bh
0x1800450e4  mov     r9, rbx
0x1800450e7  mov     rdx, rsi
0x1800450ea  mov     dword ptr [rsp+78h+var_58], edi
0x1800450ee  mov     ecx, r15d
0x1800450f1  call    AslLogCallPrintf
0x1800450f6  jmp     loc_18004550E
0x1800450fb  mov     [r12+0C4h], r15d
0x180045103  mov     ecx, [r12]; unsigned int
0x180045107  call    ?Load@CInventoryCache@@SAPEAV1@K@Z; CInventoryCache::Load(ulong)
0x18004510c  mov     [r12+2F8h], rax
0x180045114  test    rax, rax
0x180045117  jnz     loc_1800451C2
0x18004511d  lea     rbx, a0x08xFailedToI; "[0x%08x] Failed to initialize inventory"...
0x180045124  mov     r12d, 1A8h
0x18004512a  mov     edi, 80004005h
0x18004512f  mov     r9, rbx
0x180045132  mov     r8d, r12d
0x180045135  mov     dword ptr [rsp+78h+var_58], edi
0x180045139  mov     rdx, rsi
0x18004513c  mov     ecx, ebp
0x18004513e  call    AslLogCallPrintf
0x180045143  cmp     cs:EnableDevInvStdErrLog, r14d
0x18004514a  jz      short loc_18004518F
0x18004514c  mov     ecx, ebp; Ix
0x18004514e  call    _o___acrt_iob_func_0
0x180045153  mov     rcx, rax; Stream
0x180045156  lea     rdx, Format; "Error: %s, %u: "
0x18004515d  mov     r9d, r12d
0x180045160  mov     r8, rsi
0x180045163  call    fprintf
0x180045168  mov     ecx, ebp; Ix
0x18004516a  call    _o___acrt_iob_func_0
0x18004516f  mov     rcx, rax; Stream
0x180045172  mov     r8d, edi
0x180045175  mov     rdx, rbx; Format
0x180045178  call    fprintf
0x18004517d  mov     ecx, ebp; Ix
0x18004517f  call    _o___acrt_iob_func_0
0x180045184  mov     rcx, rax; Stream
0x180045187  mov     rdx, r13; Format
0x18004518a  call    fprintf
0x18004518f  cmp     cs:g_DeviceMapLogFunction, r14
0x180045196  jz      short loc_1800451A8
0x180045198  mov     r8d, edi
0x18004519b  mov     rdx, rbx
0x18004519e  mov     ecx, 2000000h
0x1800451a3  call    TraceMessageCallback
0x1800451a8  mov     r9, rbx
0x1800451ab  mov     dword ptr [rsp+78h+var_58], edi
0x1800451af  mov     r8, r12
0x1800451b2  mov     rdx, rsi
0x1800451b5  mov     ecx, r15d
0x1800451b8  call    AslLogCallPrintf
0x1800451bd  jmp     loc_180045AA6
0x1800451c2  cmp     [rbx], r14d
0x1800451c5  jz      loc_180045275
0x1800451cb  xor     edx, edx; int
0x1800451cd  mov     rcx, r12; this
0x1800451d0  call    ?AddDriverStorePackages@CDriverMap@@QEAAJH@Z; CDriverMap::AddDriverStorePackages(int)
0x1800451d5  mov     edi, eax
0x1800451d7  test    eax, eax
0x1800451d9  jns     loc_180045275
0x1800451df  lea     rbx, a0x08xFailedToA_2; "[0x%08x] Failed to add driver store dri"...
0x1800451e6  mov     dword ptr [rsp+78h+var_58], eax
0x1800451ea  mov     r9, rbx
0x1800451ed  mov     r8d, 1B2h
0x1800451f3  mov     rdx, rsi
0x1800451f6  mov     ecx, ebp
0x1800451f8  call    AslLogCallPrintf
0x1800451fd  cmp     cs:EnableDevInvStdErrLog, r14d
0x180045204  jz      short loc_18004524C
0x180045206  mov     ecx, ebp; Ix
0x180045208  call    _o___acrt_iob_func_0
0x18004520d  mov     rcx, rax; Stream
0x180045210  lea     rdx, Format; "Error: %s, %u: "
0x180045217  mov     r9d, 1B2h
0x18004521d  mov     r8, rsi
0x180045220  call    fprintf
0x180045225  mov     ecx, ebp; Ix
0x180045227  call    _o___acrt_iob_func_0
0x18004522c  mov     rcx, rax; Stream
0x18004522f  mov     r8d, edi
0x180045232  mov     rdx, rbx; Format
0x180045235  call    fprintf
0x18004523a  mov     ecx, ebp; Ix
0x18004523c  call    _o___acrt_iob_func_0
0x180045241  mov     rcx, rax; Stream
0x180045244  mov     rdx, r13; Format
0x180045247  call    fprintf
0x18004524c  cmp     cs:g_DeviceMapLogFunction, 0
0x180045254  mov     r14d, 2000000h
0x18004525a  jz      short loc_18004526A
0x18004525c  mov     r8d, edi
0x18004525f  mov     rdx, rbx
0x180045262  mov     ecx, r14d
0x180045265  call    TraceMessageCallback
0x18004526a  mov     r8d, 1B2h
0x180045270  jmp     loc_1800450E4
0x180045275  mov     rcx, r12; this
0x180045278  call    ?GetFilterDrivers@CDriverMap@@QEAAHXZ; CDriverMap::GetFilterDrivers(void)
0x18004527d  xor     ebx, ebx
0x18004527f  mov     r14d, 2000000h
0x180045285  test    eax, eax
0x180045287  jnz     loc_180045336
0x18004528d  mov     edi, 80004005h
0x180045292  lea     r9, aFailedToGetFil_0; "Failed to get filter drivers [%#x]"
0x180045299  mov     r8d, 1B9h
0x18004529f  mov     dword ptr [rsp+78h+var_58], edi
0x1800452a3  mov     rdx, rsi
0x1800452a6  mov     ecx, ebp
0x1800452a8  call    AslLogCallPrintf
0x1800452ad  cmp     cs:EnableDevInvStdErrLog, ebx
0x1800452b3  jz      short loc_1800452FF
0x1800452b5  mov     ecx, ebp; Ix
0x1800452b7  call    _o___acrt_iob_func_0
0x1800452bc  mov     rcx, rax; Stream
0x1800452bf  lea     rdx, Format; "Error: %s, %u: "
0x1800452c6  mov     r9d, 1B9h
0x1800452cc  mov     r8, rsi
0x1800452cf  call    fprintf
0x1800452d4  mov     ecx, ebp; Ix
0x1800452d6  call    _o___acrt_iob_func_0
0x1800452db  mov     rcx, rax; Stream
0x1800452de  lea     rdx, aFailedToGetFil_0; "Failed to get filter drivers [%#x]"
0x1800452e5  mov     r8d, edi
0x1800452e8  call    fprintf
0x1800452ed  mov     ecx, ebp; Ix
0x1800452ef  call    _o___acrt_iob_func_0
0x1800452f4  mov     rcx, rax; Stream
0x1800452f7  mov     rdx, r13; Format
0x1800452fa  call    fprintf
0x1800452ff  cmp     cs:g_DeviceMapLogFunction, rbx
0x180045306  jz      short loc_18004531A
0x180045308  mov     r8d, edi
0x18004530b  lea     rdx, aFailedToGetFil_0; "Failed to get filter drivers [%#x]"
0x180045312  mov     ecx, r14d
0x180045315  call    TraceMessageCallback
0x18004531a  lea     r9, aFailedToGetFil_0; "Failed to get filter drivers [%#x]"
0x180045321  mov     dword ptr [rsp+78h+var_58], edi
0x180045325  mov     r8d, 1B9h
0x18004532b  mov     rdx, rsi
0x18004532e  mov     ecx, r15d
0x180045331  call    AslLogCallPrintf
0x180045336  mov     rcx, r12; this
0x180045339  call    ?AddScmDrivers@CDriverMap@@QEAAJXZ; CDriverMap::AddScmDrivers(void)
0x18004533e  mov     edi, eax
0x180045340  test    eax, eax
0x180045342  jns     loc_1800453E2
0x180045348  lea     r9, a0x08xFailedToA_3; "[0x%08x] Failed to add SCM drivers"
0x18004534f  mov     dword ptr [rsp+78h+var_58], eax
0x180045353  mov     r8d, 1C0h
0x180045359  mov     rdx, rsi
0x18004535c  mov     ecx, ebp
0x18004535e  call    AslLogCallPrintf
0x180045363  cmp     cs:EnableDevInvStdErrLog, ebx
0x180045369  jz      short loc_1800453B5
0x18004536b  mov     ecx, ebp; Ix
0x18004536d  call    _o___acrt_iob_func_0
0x180045372  mov     rcx, rax; Stream
0x180045375  lea     rdx, Format; "Error: %s, %u: "
0x18004537c  mov     r9d, 1C0h
0x180045382  mov     r8, rsi
0x180045385  call    fprintf
0x18004538a  mov     ecx, ebp; Ix
0x18004538c  call    _o___acrt_iob_func_0
0x180045391  mov     rcx, rax; Stream
0x180045394  lea     rdx, a0x08xFailedToA_3; "[0x%08x] Failed to add SCM drivers"
0x18004539b  mov     r8d, edi
0x18004539e  call    fprintf
0x1800453a3  mov     ecx, ebp; Ix
0x1800453a5  call    _o___acrt_iob_func_0
0x1800453aa  mov     rcx, rax; Stream
0x1800453ad  mov     rdx, r13; Format
0x1800453b0  call    fprintf
0x1800453b5  cmp     cs:g_DeviceMapLogFunction, rbx
0x1800453bc  jz      short loc_1800453D0
0x1800453be  mov     r8d, edi
0x1800453c1  lea     rdx, a0x08xFailedToA_3; "[0x%08x] Failed to add SCM drivers"
0x1800453c8  mov     ecx, r14d
0x1800453cb  call    TraceMessageCallback
0x1800453d0  lea     r9, a0x08xFailedToA_3; "[0x%08x] Failed to add SCM drivers"
0x1800453d7  mov     r8d, 1C0h
0x1800453dd  jmp     loc_1800450E7
0x1800453e2  mov     rcx, r12; this
0x1800453e5  call    ?AddUserDrivers@CDriverMap@@AEAAJXZ; CDriverMap::AddUserDrivers(void)
0x1800453ea  xor     edi, edi
0x1800453ec  mov     ebx, eax
0x1800453ee  test    eax, eax
0x1800453f0  jns     loc_18004549A
0x1800453f6  lea     r9, a0x08xFailedToA; "[0x%08x] Failed to add user mode driver"...
  ... truncated ...
```
