# WriteFullMemory(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *)

- ea: `0x18000c67c`
- end: `0x18000d221`
- name: `?WriteFullMemory@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@@Z`
- size: `2981`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _MINIDUMP_STREAM_INFO *, struct _INTERNAL_PROCESS *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000c19c`

## callees

- `0x180001710`
- `0x180006b0c`
- `0x18000bcbc`
- `0x18000c67c`
- `0x18001951c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-misc-l1-1-0!Sleep` at `0x18000cb33`
- `api-ms-win-core-misc-l1-1-0!Sleep` at `0x18000ce68`
- `api-ms-win-core-misc-l1-1-0!Sleep` at `0x18000cb33`
- `api-ms-win-core-misc-l1-1-0!Sleep` at `0x18000ce68`

## string_xrefs

- `0x18000d1c4`: `WriteFullMemory.QueryVirtual(0x%I64x) for info failed, 0x%08x`
- `0x18000cef5`: `WriteFullMemory.Desc.Write(0x%x) failed, 0x%08x`
- `0x18000d15e`: `WriteFullMemory.QueryVirtual(0x%I64x) for data failed, 0x%08x`
- `0x18000cc74`: `WriteFullMemory.Memory.Read(0x%I64x, 0x%x) failed 0x%08x, skip.`
- `0x18000cfa9`: `WriteFullMemory.Memory.Read(0x%I64x, 0x%x) failed 0x%08x, ABORT.`
- `0x18000cfe9`: `WriteFullMemory.Memory.Write(0x%x) failed, 0x%08x`
- `0x18000cf73`: `Too many inaccessible memory blocks, bail out.`
- `0x18000cd91`: `WriteFullMemory.Memory.Read(0x%I64x, 0x%x) partial read of 0x%x, split.`
- `0x18000ce41`: `WriteFullMemory virtual memory layout changed, retries %d, 0x%I64x (0x%I64x:0x%I64x) vs. 0x%I64x (0x%I64x:0x%I64x)`
- `0x18000d0ee`: `Could not update MINIDUMP_MEMORY_DESCRIPTOR64::DataSize value for range# %I64d at RVA 0x%016I64X`

## pseudocode

```c
__int64 __fastcall WriteFullMemory(
        struct _MINIDUMP_STATE *a1,
        struct _MINIDUMP_STREAM_INFO *a2,
        struct _INTERNAL_PROCESS *a3)
{
  unsigned int v5; // r15d
  unsigned int v6; // edx
  int v7; // r14d
  __int64 v8; // r13
  __int64 v9; // r12
  ULONG64 v10; // rbx
  unsigned __int64 v11; // rdi
  struct _MINIDUMP_STATE *v12; // r10
  ULONG64 BaseAddress; // r9
  __int64 RegionSize; // r8
  unsigned int v15; // edi
  __int64 v16; // rdx
  unsigned int v17; // esi
  char *v18; // r13
  __int64 v19; // rdi
  ULONG64 v20; // rdx
  ULONG64 v21; // rsi
  __int64 v22; // rcx
  ULONG64 v23; // r14
  unsigned __int64 v24; // r12
  ULONG64 v25; // r13
  unsigned __int64 v26; // rbx
  unsigned int v27; // ebx
  __int64 v28; // rsi
  int v29; // r15d
  char *v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rcx
  void (*v34)(__int64, __int64, const char *, ...); // rax
  int v35; // edx
  __int64 v36; // r9
  struct _MINIDUMP_STATE *v37; // r10
  unsigned int v38; // r15d
  unsigned int v39; // r12d
  unsigned int v40; // r14d
  unsigned int v41; // edi
  int v42; // eax
  unsigned int v43; // ebx
  __int64 v44; // rbx
  struct _MINIDUMP_STREAM_INFO *v45; // r14
  unsigned int v46; // edx
  struct _MINIDUMP_STREAM_INFO *v47; // rsi
  __int64 v48; // [rsp+20h] [rbp-E0h]
  __int64 v49; // [rsp+28h] [rbp-D8h]
  struct _MINIDUMP_STATE *v50; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v51; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v52; // [rsp+78h] [rbp-88h]
  __int64 v53; // [rsp+80h] [rbp-80h]
  ULONG64 v54; // [rsp+88h] [rbp-78h]
  int v55; // [rsp+90h] [rbp-70h]
  unsigned int v56; // [rsp+94h] [rbp-6Ch]
  char *v57; // [rsp+98h] [rbp-68h]
  __int64 v58; // [rsp+A0h] [rbp-60h]
  __int64 v59; // [rsp+A8h] [rbp-58h]
  struct _MINIDUMP_STREAM_INFO *v60; // [rsp+B0h] [rbp-50h]
  ULONG64 v61; // [rsp+B8h] [rbp-48h]
  __int64 v62; // [rsp+C0h] [rbp-40h]
  char *i; // [rsp+C8h] [rbp-38h]
  char *v64; // [rsp+D0h] [rbp-30h]
  __int64 v65; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v66; // [rsp+E0h] [rbp-20h]
  struct _INTERNAL_PROCESS *v67; // [rsp+E8h] [rbp-18h]
  __int64 v68; // [rsp+F0h] [rbp-10h]
  struct _MINIDUMP_STATE **v69; // [rsp+F8h] [rbp-8h]
  __int64 *v70; // [rsp+100h] [rbp+0h]
  char v71; // [rsp+108h] [rbp+8h]
  __int128 v72; // [rsp+110h] [rbp+10h] BYREF
  struct _MINIDUMP_MEMORY_INFO v73; // [rsp+120h] [rbp+20h] BYREF
  __int128 v74; // [rsp+150h] [rbp+50h] BYREF

  v68 = -2;
  v67 = a3;
  v60 = a2;
  v50 = a1;
  v72 = 0;
  v74 = 0;
  memset(&v73, 0, sizeof(v73));
  v51 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)a1 + 4) + 8LL))(*((_QWORD *)a1 + 4), 20480);
  if ( !v51 )
    return 2147942414LL;
  v69 = &v50;
  v70 = &v51;
  v71 = 1;
  if ( *((_QWORD *)a2 + 20) > 0xFFFFFFFF )
  {
    (*(void (__fastcall **)(_QWORD, __int64, const char *))(**((_QWORD **)v50 + 5) + 8LL))(
      *((_QWORD *)v50 + 5),
      4,
      "Full memory stream RVA overflowed");
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v50 + 4) + 24LL))(*((_QWORD *)v50 + 4), v51);
    return 2147942487LL;
  }
  v56 = 5;
  v5 = 0;
  v52 = 0;
  v6 = *((_DWORD *)a2 + 40);
  *((_DWORD *)a2 + 26) = v6;
LABEL_107:
  v72 = 0;
  v27 = WriteAtOffset(v50, v6, &v72, 0x10u);
  if ( v27 )
  {
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v50 + 4) + 24LL))(*((_QWORD *)v50 + 4), v51);
    return v27;
  }
  v7 = 1;
  v64 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
LABEL_8:
  v59 = v9;
  v58 = v8;
LABEL_9:
  v12 = v50;
  while ( 1 )
  {
    if ( !v10 && v11 )
      goto LABEL_38;
    if ( (unsigned int)GenCheckCancel(v12) )
    {
LABEL_129:
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v50 + 4) + 24LL))(*((_QWORD *)v50 + 4), v51);
      return 2147943623LL;
    }
    if ( v11 && v10 <= v11 )
    {
      BaseAddress = v10;
      v73.BaseAddress = v10;
      RegionSize = v11 - v10 + 1;
      v73.RegionSize = RegionSize;
      goto LABEL_18;
    }
    v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, ULONG64, struct _MINIDUMP_MEMORY_INFO *))(**((_QWORD **)v50 + 2)
                                                                                             + 248LL))(
            *((_QWORD *)v50 + 2),
            *(_QWORD *)v50,
            v10,
            &v73);
    if ( v15 )
      break;
    RegionSize = v73.RegionSize;
    BaseAddress = v73.BaseAddress;
LABEL_18:
    v10 = RegionSize + BaseAddress;
    v11 = RegionSize + BaseAddress - 1;
    if ( (v73.Protect & 0x100) != 0 || (v73.Protect & 1) != 0 || (v73.State & 0x10000) != 0 || (v73.State & 0x2000) != 0 )
      goto LABEL_9;
    v12 = v50;
    if ( (*((_DWORD *)v50 + 14) & 0x1000000) == 0 || (v73.Protect & 0x400) == 0 )
    {
      if ( !v7 )
        goto LABEL_27;
      v7 = FilterVmRegion(v50, &v73);
      RegionSize = v73.RegionSize;
      if ( !v73.RegionSize )
        goto LABEL_9;
      BaseAddress = v73.BaseAddress;
      v10 = v73.RegionSize + v73.BaseAddress;
      v12 = v50;
LABEL_27:
      if ( (_QWORD)v72 == 268435454 )
      {
        (*(void (__fastcall **)(_QWORD, __int64, const char *))(**((_QWORD **)v12 + 5) + 8LL))(
          *((_QWORD *)v12 + 5),
          4,
          "Full memory stream overflowed");
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v50 + 4) + 24LL))(*((_QWORD *)v50 + 4), v51);
        return 2147942487LL;
      }
      *(_QWORD *)&v72 = v72 + 1;
      v16 = 0;
      if ( v5 )
      {
        while ( *(_QWORD *)(v51 + 20 * v16) != BaseAddress )
        {
          v16 = (unsigned int)(v16 + 1);
          if ( (unsigned int)v16 >= v5 )
            goto LABEL_34;
        }
        RegionSize = *(unsigned int *)(v51 + 20 * v16 + 16);
        if ( *(_DWORD *)(v51 + 20 * v16 + 16) )
        {
          v73.RegionSize = *(unsigned int *)(v51 + 20 * v16 + 16);
          v10 = ~(unsigned __int64)(unsigned int)(*((_DWORD *)v12 + 40) - 1)
              & (*(unsigned int *)(v51 + 20 * v16 + 16) + BaseAddress + *((unsigned int *)v12 + 40) - 1LL);
        }
      }
LABEL_34:
      *(_QWORD *)&v74 = BaseAddress;
      *((_QWORD *)&v74 + 1) = RegionSize;
      v17 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64))(**((_QWORD **)v12 + 3) + 32LL))(
              *((_QWORD *)v12 + 3),
              &v74,
              16);
      if ( v17 )
      {
        (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)v50 + 5) + 8LL))(
          *((_QWORD *)v50 + 5),
          4,
          "WriteFullMemory.Desc.Write(0x%x) failed, 0x%08x");
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v50 + 4) + 24LL))(*((_QWORD *)v50 + 4), v51);
        return v17;
      }
      v64 += v73.RegionSize;
      ++v8;
      v9 += v73.BaseAddress;
      goto LABEL_8;
    }
  }
  if ( v15 != -2147467262 )
  {
    LODWORD(v48) = v15;
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)v50 + 5) + 8LL))(
      *((_QWORD *)v50 + 5),
      4,
      "WriteFullMemory.QueryVirtual(0x%I64x) for info failed, 0x%08x",
      v10,
      v48);
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v50 + 4) + 24LL))(*((_QWORD *)v50 + 4), v51);
    return v15;
  }
  v12 = v50;
LABEL_38:
  *((_QWORD *)&v72 + 1) = *((unsigned int *)v60 + 26) + 16 * (v72 + 1);
  v55 = 1;
  v18 = 0;
  v57 = 0;
  v19 = 0;
  v62 = 0;
  v20 = 0;
  v54 = 0;
  v21 = 0;
  v61 = 0;
  v22 = 0;
  v53 = 0;
  v65 = 0;
  v23 = 0;
  v24 = 0;
  while ( 1 )
  {
    if ( !v23 && v24 )
      goto LABEL_101;
    if ( (unsigned int)GenCheckCancel(v12) )
      goto LABEL_129;
    if ( !v24 || v23 > v24 )
      break;
    v25 = v23;
    v73.BaseAddress = v23;
    v26 = v24 - v23 + 1;
    v73.RegionSize = v26;
LABEL_48:
    v23 = v26 + v25;
    v24 = v26 + v25 - 1;
    if ( (v73.Protect & 0x100) != 0 || (v73.Protect & 1) != 0 || (v73.State & 0x10000) != 0 || (v73.State & 0x2000) != 0 )
    {
LABEL_56:
      v12 = v50;
      v20 = v54;
      v22 = v53;
LABEL_39:
      v18 = v57;
      continue;
    }
    v12 = v50;
    if ( (*((_DWORD *)v50 + 14) & 0x1000000) != 0 )
    {
      v20 = v54;
      v22 = v53;
      if ( (v73.Protect & 0x400) != 0 )
        goto LABEL_39;
    }
    if ( v55 )
    {
      v55 = FilterVmRegion(v50, &v73);
      v26 = v73.RegionSize;
      if ( !v73.RegionSize )
        goto LABEL_56;
      v25 = v73.BaseAddress;
      v23 = v73.RegionSize + v73.BaseAddress;
      v12 = v50;
    }
    v28 = 0;
    if ( v5 )
    {
      while ( *(_QWORD *)(v51 + 20 * v28) != v25 )
      {
        v28 = (unsigned int)(v28 + 1);
        if ( (unsigned int)v28 >= v5 )
          goto LABEL_61;
      }
      v31 = *(unsigned int *)(v51 + 20 * v28 + 16);
      if ( (_DWORD)v31 )
      {
        v26 = (unsigned int)v31;
        v73.RegionSize = *(unsigned int *)(v51 + 20 * v28 + 16);
        v23 = ~(unsigned __int64)(unsigned int)(*((_DWORD *)v12 + 40) - 1)
            & (v25 + v31 + *((unsigned int *)v12 + 40) - 1LL);
      }
      if ( !*(_DWORD *)(v51 + 20 * v28 + 16) )
      {
        v32 = v53;
        *(_QWORD *)(v51 + 20 * v28 + 8) = v53 + v19;
        *(_DWORD *)(v51 + 20 * v28 + 16) = 0;
        v21 = v73.RegionSize + v61;
        v61 += v73.RegionSize;
        v22 = v32 + 1;
        v53 = v22;
        v65 += v73.BaseAddress;
        v12 = v50;
        v20 = v54;
        goto LABEL_39;
      }
    }
LABEL_61:
    v66 = v26;
    while ( 2 )
    {
      if ( v26 )
      {
        if ( v26 > 0x10000 )
          LODWORD(v26) = 0x10000;
        v29 = 5;
        v30 = (char *)v67 + 7608;
        for ( i = (char *)v67 + 7608; ; v30 = i )
        {
          v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, ULONG64, char *, _DWORD))(**((_QWORD **)v12 + 2) + 240LL))(
                  *((_QWORD *)v12 + 2),
                  *(_QWORD *)v12,
                  v25,
                  v30,
                  v26);
          if ( !v15 )
            break;
          --v29;
          Sleep(0xFAu);
          if ( !v29 )
          {
            LODWORD(v49) = v15;
            LODWORD(v48) = v26;
            v33 = *((_QWORD *)v50 + 5);
            v34 = *(void (**)(__int64, __int64, const char *, ...))(*(_QWORD *)v33 + 8LL);
            if ( (*((_DWORD *)v50 + 14) & 0x20000) == 0 )
            {
              v34(v33, 4, "WriteFullMemory.Memory.Read(0x%I64x, 0x%x) failed 0x%08x, ABORT.", v25, v48, v49);
              (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v50 + 4) + 24LL))(*((_QWORD *)v50 + 4), v51);
              return v15;
            }
            v34(v33, 4, "WriteFullMemory.Memory.Read(0x%I64x, 0x%x) failed 0x%08x, skip.", v25, v48, v49);
            v5 = v52;
            if ( (unsigned int)v28 >= v52 )
            {
              v35 = 0;
              LODWORD(v28) = v52;
            }
            else
            {
              v35 = *(_DWORD *)(v51 + 20 * v28 + 16);
            }
            if ( v52 >= 0x400 )
            {
              (*(void (__fastcall **)(_QWORD, __int64, const char *))(**((_QWORD **)v50 + 5) + 8LL))(
                *((_QWORD *)v50 + 5),
                4,
                "Too many inaccessible memory blocks, bail out.");
              (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v50 + 4) + 24LL))(*((_QWORD *)v50 + 4), v51);
              return v15;
            }
            v36 = 5LL * (unsigned int)v28;
            v58 = v36;
            *(_QWORD *)(v51 + 4 * v36) = v73.BaseAddress;
            *(_QWORD *)(v51 + 4 * v36 + 8) = v62 + v53;
            *(_DWORD *)(v51 + 4 * v36 + 16) = 0;
            v37 = v50;
            v66 = (unsigned __int64)v50;
            if ( (*((_DWORD *)v50 + 14) & 0x800000) == 0 || v15 != -2147024597 || v35 )
              goto LABEL_97;
            v38 = 0;
            v39 = v26;
            v40 = 0;
            while ( 1 )
            {
              v41 = (v39 + v38) >> 1;
              v42 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, ULONG64, char *, unsigned int))(**((_QWORD **)v37 + 2)
                                                                                             + 240LL))(
                      *((_QWORD *)v37 + 2),
                      *(_QWORD *)v37,
                      v25,
                      i,
                      v41);
              if ( v42 < 0 )
              {
                if ( v42 != -2147024597 )
                  goto LABEL_96;
                if ( v40 && v40 + v38 + 1 == v41 )
                  goto LABEL_95;
                if ( v41 <= v38 )
                {
LABEL_94:
                  if ( !v40 )
                    goto LABEL_96;
LABEL_95:
                  LODWORD(v49) = v40;
                  LODWORD(v48) = v26;
                  (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)v50 + 5) + 8LL))(
                    *((_QWORD *)v50 + 5),
                    2,
                    "WriteFullMemory.Memory.Read(0x%I64x, 0x%x) partial read of 0x%x, split.",
                    v25,
                    v48,
                    v49);
                  *(_DWORD *)(v51 + 4 * v58 + 16) = v40;
LABEL_96:
                  v5 = v52;
LABEL_97:
                  if ( (_DWORD)v28 == v5 )
                    v52 = ++v5;
LABEL_106:
                  v6 = *((_DWORD *)v60 + 26);
                  goto LABEL_107;
                }
                v39 = v41 - 1;
              }
              else
              {
                v40 = (v39 + v38) >> 1;
                if ( v41 >= v39 )
                  goto LABEL_94;
                v38 = v41 + 1;
              }
              v37 = (struct _MINIDUMP_STATE *)v66;
              if ( v38 > v39 )
                goto LABEL_94;
            }
          }
          v12 = v50;
        }
        v15 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)v50 + 3) + 32LL))(
                *((_QWORD *)v50 + 3),
                i,
                (unsigned int)v26);
        if ( !v15 )
        {
          v25 += (unsigned int)v26;
          v26 = v73.RegionSize - (unsigned int)v26;
          v73.RegionSize = v26;
          v12 = v50;
          continue;
        }
        LODWORD(v48) = v15;
        (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)v50 + 5) + 8LL))(
          *((_QWORD *)v50 + 5),
          4,
          "WriteFullMemory.Memory.Write(0x%x) failed, 0x%08x",
          (unsigned int)v26,
          v48);
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v50 + 4) + 24LL))(*((_QWORD *)v50 + 4), v51);
        return v15;
      }
      break;
    }
    v18 = &v57[v66];
    v57 += v66;
    v19 = ++v62;
    v20 = v73.BaseAddress + v54;
    v54 += v73.BaseAddress;
    v5 = v52;
    v22 = v53;
    v21 = v61;
  }
  v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, ULONG64, struct _MINIDUMP_MEMORY_INFO *))(**((_QWORD **)v50 + 2)
                                                                                           + 248LL))(
          *((_QWORD *)v50 + 2),
          *(_QWORD *)v50,
          v23,
          &v73);
  if ( !v27 )
  {
    v26 = v73.RegionSize;
    v25 = v73.BaseAddress;
    goto LABEL_48;
  }
  if ( v27 != -2147467262 )
  {
    LODWORD(v48) = v27;
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)v50 + 5) + 8LL))(
      *((_QWORD *)v50 + 5),
      4,
      "WriteFullMemory.QueryVirtual(0x%I64x) for data failed, 0x%08x",
      v23,
      v48);
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v50 + 4) + 24LL))(*((_QWORD *)v50 + 4), v51);
    return v27;
  }
  v12 = v50;
  v20 = v54;
  v22 = v53;
LABEL_101:
  if ( v64 != &v18[v21] || v58 != v22 + v19 || v59 != v20 + v65 )
  {
    v43 = v56;
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)v12 + 5) + 8LL))(
      *((_QWORD *)v12 + 5),
      4,
      "WriteFullMemory virtual memory layout changed, retries %d, 0x%I64x (0x%I64x:0x%I64x) vs. 0x%I64x (0x%I64x:0x%I64x)",
      v56,
      v64,
      v58,
      v59,
      v18,
      v19,
      v20);
    v56 = v43 - 1;
    if ( (int)(v43 - 1) > 0 )
    {
      Sleep(0xFAu);
      goto LABEL_106;
    }
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v50 + 4) + 24LL))(*((_QWORD *)v50 + 4), v51);
    return 2147942413LL;
  }
  v44 = 0;
  if ( !v5 )
  {
LABEL_121:
    v47 = v60;
    *((_DWORD *)v60 + 27) += 16 * v72;
    *((_QWORD *)v47 + 20) = &v18[*((_QWORD *)&v72 + 1)];
    v27 = WriteAtOffset(v12, *((_DWORD *)v47 + 26), &v72, 0x10u);
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v50 + 4) + 24LL))(*((_QWORD *)v50 + 4), v51);
    return v27;
  }
  v45 = v60;
  while ( 2 )
  {
    if ( *(_DWORD *)(v51 + 20 * v44 + 16) )
    {
LABEL_120:
      v44 = (unsigned int)(v44 + 1);
      if ( (unsigned int)v44 >= v5 )
        goto LABEL_121;
      continue;
    }
    break;
  }
  v46 = *((_DWORD *)v45 + 26) + 16 * (*(_DWORD *)(v51 + 20 * v44 + 8) + 1);
  v74 = *(unsigned __int64 *)(v51 + 20 * v44);
  v17 = WriteAtOffset(v12, v46, &v74, 0x10u);
  if ( !v17 )
  {
    v12 = v50;
    goto LABEL_120;
  }
  (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)v50 + 5) + 8LL))(
    *((_QWORD *)v50 + 5),
    4,
    "Could not update MINIDUMP_MEMORY_DESCRIPTOR64::DataSize value for range# %I64d at RVA 0x%016I64X",
    *(_QWORD *)(v51 + 20 * v44 + 8),
    *(_QWORD *)(v51 + 20 * v44));
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v50 + 4) + 24LL))(*((_QWORD *)v50 + 4), v51);
  return v17;
}

```

## disassembly

```asm
0x18000c67c  mov     rax, rsp
0x18000c67f  push    rbp
0x18000c680  push    rsi
0x18000c681  push    rdi
0x18000c682  push    r12
0x18000c684  push    r13
0x18000c686  push    r14
0x18000c688  push    r15
0x18000c68a  lea     rbp, [rsp-70h]
0x18000c68f  sub     rsp, 170h
0x18000c696  mov     [rbp+0A0h+var_B0], 0FFFFFFFFFFFFFFFEh
0x18000c69e  mov     [rax+20h], rbx
0x18000c6a2  mov     rax, cs:__security_cookie
0x18000c6a9  xor     rax, rsp
0x18000c6ac  mov     [rbp+0A0h+var_40], rax
0x18000c6b0  mov     [rbp+0A0h+var_B8], r8
0x18000c6b4  mov     rsi, rdx
0x18000c6b7  mov     [rbp+0A0h+var_F0], rdx
0x18000c6bb  mov     [rsp+1A0h+var_140], rcx
0x18000c6c0  xorps   xmm0, xmm0
0x18000c6c3  movups  [rbp+0A0h+var_90], xmm0
0x18000c6c7  xorps   xmm1, xmm1
0x18000c6ca  movups  [rbp+0A0h+var_50], xmm1
0x18000c6ce  movups  xmmword ptr [rbp+0A0h+var_80.BaseAddress], xmm0
0x18000c6d2  movups  xmmword ptr [rbp+0A0h+var_80.AllocationProtect], xmm0
0x18000c6d6  movups  xmmword ptr [rbp+0A0h+var_80.State], xmm0
0x18000c6da  mov     rcx, [rcx+20h]
0x18000c6de  mov     rax, [rcx]
0x18000c6e1  mov     edx, 5000h
0x18000c6e6  mov     rax, [rax+8]
0x18000c6ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6ef  mov     [rsp+1A0h+var_130], rax
0x18000c6f4  test    rax, rax
0x18000c6f7  jnz     short loc_18000C703
0x18000c6f9  mov     eax, 8007000Eh
0x18000c6fe  jmp     loc_18000CEB8
0x18000c703  lea     rax, [rsp+1A0h+var_140]
0x18000c708  mov     [rbp+0A0h+var_A8], rax
0x18000c70c  lea     rax, [rsp+1A0h+var_130]
0x18000c711  mov     [rbp+0A0h+var_A0], rax
0x18000c715  mov     [rbp+0A0h+var_98], 1
0x18000c719  mov     eax, 0FFFFFFFFh
0x18000c71e  cmp     [rsi+0A0h], rax
0x18000c725  jbe     short loc_18000C76E
0x18000c727  mov     rax, [rsp+1A0h+var_140]
0x18000c72c  mov     rcx, [rax+28h]
0x18000c730  mov     rax, [rcx]
0x18000c733  lea     r8, aFullMemoryStre_0; "Full memory stream RVA overflowed"
0x18000c73a  mov     edx, 4
0x18000c73f  mov     rax, [rax+8]
0x18000c743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c748  nop
0x18000c749  mov     rax, [rsp+1A0h+var_140]
0x18000c74e  mov     rcx, [rax+20h]
0x18000c752  mov     rax, [rcx]
0x18000c755  mov     rdx, [rsp+1A0h+var_130]
0x18000c75a  mov     rax, [rax+18h]
0x18000c75e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c763  nop
0x18000c764  mov     eax, 80070057h
0x18000c769  jmp     loc_18000CEB8
0x18000c76e  mov     [rbp+0A0h+var_10C], 5
0x18000c775  xor     r15d, r15d
0x18000c778  mov     [rsp+1A0h+var_128], r15d
0x18000c77d  mov     edx, [rsi+0A0h]
0x18000c783  mov     [rsi+68h], edx
0x18000c786  jmp     loc_18000CE76
0x18000c78b  mov     r14d, 1
0x18000c791  xor     r11d, r11d
0x18000c794  mov     [rbp+0A0h+var_D0], r11
0x18000c798  xor     r13d, r13d
0x18000c79b  xor     r12d, r12d
0x18000c79e  xor     ebx, ebx
0x18000c7a0  xor     edi, edi
0x18000c7a2  mov     [rbp+0A0h+var_F8], r12
0x18000c7a6  mov     [rbp+0A0h+var_100], r13
0x18000c7aa  mov     r10, [rsp+1A0h+var_140]
0x18000c7af  test    rbx, rbx
0x18000c7b2  jnz     short loc_18000C7BD
0x18000c7b4  test    rdi, rdi
0x18000c7b7  jnz     loc_18000C95B
0x18000c7bd  mov     rcx, r10; struct _MINIDUMP_STATE *
0x18000c7c0  call    ?GenCheckCancel@@YAHPEAU_MINIDUMP_STATE@@@Z; GenCheckCancel(_MINIDUMP_STATE *)
0x18000c7c5  test    eax, eax
0x18000c7c7  jnz     loc_18000D1FC
0x18000c7cd  test    rdi, rdi
0x18000c7d0  jz      short loc_18000C7ED
0x18000c7d2  cmp     rbx, rdi
0x18000c7d5  ja      short loc_18000C7ED
0x18000c7d7  mov     r9, rbx
0x18000c7da  mov     [rbp+0A0h+var_80.BaseAddress], rbx
0x18000c7de  sub     rdi, rbx
0x18000c7e1  inc     rdi
0x18000c7e4  mov     r8, rdi
0x18000c7e7  mov     [rbp+0A0h+var_80.RegionSize], rdi
0x18000c7eb  jmp     short loc_18000C821
0x18000c7ed  mov     rdx, [rsp+1A0h+var_140]
0x18000c7f2  mov     rcx, [rdx+10h]
0x18000c7f6  mov     rax, [rcx]
0x18000c7f9  lea     r9, [rbp+0A0h+var_80]
0x18000c7fd  mov     r8, rbx
0x18000c800  mov     rdx, [rdx]
0x18000c803  mov     rax, [rax+0F8h]
0x18000c80a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c80f  mov     edi, eax
0x18000c811  test    eax, eax
0x18000c813  jnz     loc_18000C94A
0x18000c819  mov     r8, [rbp+0A0h+var_80.RegionSize]
0x18000c81d  mov     r9, [rbp+0A0h+var_80.BaseAddress]
0x18000c821  lea     rbx, [r8+r9]
0x18000c825  lea     rdi, [rbx-1]
0x18000c829  mov     eax, [rbp+0A0h+var_80.Protect]
0x18000c82c  bt      eax, 8
0x18000c830  jb      loc_18000C7AA
0x18000c836  test    al, 1
0x18000c838  jnz     loc_18000C7AA
0x18000c83e  test    [rbp+0A0h+var_80.State], 10000h
0x18000c845  jnz     loc_18000C7AA
0x18000c84b  test    [rbp+0A0h+var_80.State], 2000h
0x18000c852  jnz     loc_18000C7AA
0x18000c858  mov     r10, [rsp+1A0h+var_140]
0x18000c85d  test    dword ptr [r10+38h], 1000000h
0x18000c865  jz      short loc_18000C871
0x18000c867  bt      eax, 0Ah
0x18000c86b  jb      loc_18000C7AF
0x18000c871  test    r14d, r14d
0x18000c874  jz      short loc_18000C89F
0x18000c876  lea     rdx, [rbp+0A0h+var_80]; struct _MINIDUMP_MEMORY_INFO *
0x18000c87a  mov     rcx, r10; struct _MINIDUMP_STATE *
0x18000c87d  call    ?FilterVmRegion@@YAHPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_MEMORY_INFO@@@Z; FilterVmRegion(_MINIDUMP_STATE *,_MINIDUMP_MEMORY_INFO *)
0x18000c882  mov     r14d, eax
0x18000c885  mov     r8, [rbp+0A0h+var_80.RegionSize]
0x18000c889  test    r8, r8
0x18000c88c  jz      loc_18000C7AA
0x18000c892  mov     r9, [rbp+0A0h+var_80.BaseAddress]
0x18000c896  lea     rbx, [r8+r9]
0x18000c89a  mov     r10, [rsp+1A0h+var_140]
0x18000c89f  mov     rax, qword ptr [rbp+0A0h+var_90]
0x18000c8a3  cmp     rax, 0FFFFFFEh
0x18000c8a9  jz      loc_18000CF2A
0x18000c8af  inc     rax
0x18000c8b2  mov     qword ptr [rbp+0A0h+var_90], rax
0x18000c8b6  xor     edx, edx
0x18000c8b8  test    r15d, r15d
0x18000c8bb  jz      short loc_18000C906
0x18000c8bd  mov     r11, [rsp+1A0h+var_130]
0x18000c8c2  lea     rcx, [rdx+rdx*4]
0x18000c8c6  cmp     [r11+rcx*4], r9
0x18000c8ca  jz      short loc_18000C8D5
0x18000c8cc  inc     edx
0x18000c8ce  cmp     edx, r15d
0x18000c8d1  jb      short loc_18000C8C2
0x18000c8d3  jmp     short loc_18000C906
0x18000c8d5  lea     rcx, [rdx+rdx*4]
0x18000c8d9  mov     r8d, [r11+rcx*4+10h]
0x18000c8de  test    r8, r8
0x18000c8e1  jz      short loc_18000C906
0x18000c8e3  mov     [rbp+0A0h+var_80.RegionSize], r8
0x18000c8e7  mov     edx, [r10+0A0h]
0x18000c8ee  mov     ecx, [r11+rcx*4+10h]
0x18000c8f3  lea     rbx, [rdx-1]
0x18000c8f7  add     rbx, r9
0x18000c8fa  add     rbx, rcx
0x18000c8fd  lea     ecx, [rdx-1]
0x18000c900  not     rcx
0x18000c903  and     rbx, rcx
0x18000c906  mov     qword ptr [rbp+0A0h+var_50], r9
0x18000c90a  mov     qword ptr [rbp+0A0h+var_50+8], r8
0x18000c90e  mov     rcx, [r10+18h]
0x18000c912  mov     rax, [rcx]
0x18000c915  mov     r8d, 10h
0x18000c91b  lea     rdx, [rbp+0A0h+var_50]
0x18000c91f  mov     rax, [rax+20h]
0x18000c923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c928  mov     esi, eax
0x18000c92a  test    eax, eax
0x18000c92c  jnz     loc_18000CEDF
0x18000c932  mov     rax, [rbp+0A0h+var_D0]
0x18000c936  add     rax, [rbp+0A0h+var_80.RegionSize]
0x18000c93a  mov     [rbp+0A0h+var_D0], rax
0x18000c93e  inc     r13
0x18000c941  add     r12, [rbp+0A0h+var_80.BaseAddress]
0x18000c945  jmp     loc_18000C7A2
0x18000c94a  cmp     edi, 80004002h
0x18000c950  jnz     loc_18000D1B1
0x18000c956  mov     r10, [rsp+1A0h+var_140]
0x18000c95b  mov     rcx, qword ptr [rbp+0A0h+var_90]
0x18000c95f  inc     rcx
0x18000c962  shl     rcx, 4
0x18000c966  mov     r9, [rbp+0A0h+var_F0]
0x18000c96a  mov     eax, [r9+68h]
0x18000c96e  add     rcx, rax
0x18000c971  mov     qword ptr [rbp+0A0h+var_90+8], rcx
0x18000c975  mov     [rbp+0A0h+var_110], 1
0x18000c97c  xor     r13d, r13d
0x18000c97f  mov     [rbp+0A0h+var_108], r13
0x18000c983  xor     edi, edi
0x18000c985  mov     [rbp+0A0h+var_E0], rdi
0x18000c989  xor     edx, edx
0x18000c98b  mov     [rbp+0A0h+var_118], rdx
0x18000c98f  xor     esi, esi
0x18000c991  mov     [rbp+0A0h+var_E8], rsi
0x18000c995  xor     ecx, ecx
0x18000c997  mov     [rbp+0A0h+var_120], rcx
0x18000c99b  xor     eax, eax
0x18000c99d  mov     [rbp+0A0h+var_C8], rax
0x18000c9a1  xor     r14d, r14d
0x18000c9a4  xor     r12d, r12d
0x18000c9a7  jmp     short loc_18000C9AD
0x18000c9a9  mov     r13, [rbp+0A0h+var_108]
0x18000c9ad  test    r14, r14
0x18000c9b0  jnz     short loc_18000C9BB
0x18000c9b2  test    r12, r12
0x18000c9b5  jnz     loc_18000CDE8
0x18000c9bb  mov     rcx, r10; struct _MINIDUMP_STATE *
0x18000c9be  call    ?GenCheckCancel@@YAHPEAU_MINIDUMP_STATE@@@Z; GenCheckCancel(_MINIDUMP_STATE *)
0x18000c9c3  test    eax, eax
0x18000c9c5  jnz     loc_18000D194
0x18000c9cb  test    r12, r12
0x18000c9ce  jz      short loc_18000C9EA
0x18000c9d0  cmp     r14, r12
0x18000c9d3  ja      short loc_18000C9EA
0x18000c9d5  mov     r13, r14
0x18000c9d8  mov     [rbp+0A0h+var_80.BaseAddress], r14
0x18000c9dc  sub     r12, r14
0x18000c9df  lea     rbx, [r12+1]
0x18000c9e4  mov     [rbp+0A0h+var_80.RegionSize], rbx
0x18000c9e8  jmp     short loc_18000CA1E
0x18000c9ea  mov     rdx, [rsp+1A0h+var_140]
0x18000c9ef  mov     rcx, [rdx+10h]
0x18000c9f3  mov     rax, [rcx]
0x18000c9f6  lea     r9, [rbp+0A0h+var_80]
0x18000c9fa  mov     r8, r14
0x18000c9fd  mov     rdx, [rdx]
0x18000ca00  mov     rax, [rax+0F8h]
0x18000ca07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca0c  mov     ebx, eax
0x18000ca0e  test    eax, eax
0x18000ca10  jnz     loc_18000CDCF
0x18000ca16  mov     rbx, [rbp+0A0h+var_80.RegionSize]
0x18000ca1a  mov     r13, [rbp+0A0h+var_80.BaseAddress]
0x18000ca1e  lea     r14, [rbx+r13]
0x18000ca22  lea     r12, [r14-1]
0x18000ca26  mov     eax, [rbp+0A0h+var_80.Protect]
0x18000ca29  bt      eax, 8
0x18000ca2d  jb      short loc_18000CA87
0x18000ca2f  test    al, 1
0x18000ca31  jnz     short loc_18000CA87
0x18000ca33  mov     r9d, 10000h
0x18000ca39  test    [rbp+0A0h+var_80.State], r9d
0x18000ca3d  jnz     short loc_18000CA87
0x18000ca3f  test    [rbp+0A0h+var_80.State], 2000h
0x18000ca46  jnz     short loc_18000CA87
0x18000ca48  mov     r10, [rsp+1A0h+var_140]
0x18000ca4d  test    dword ptr [r10+38h], 1000000h
0x18000ca55  jz      short loc_18000CA69
0x18000ca57  bt      eax, 0Ah
0x18000ca5b  mov     rdx, [rbp+0A0h+var_118]
0x18000ca5f  mov     rcx, [rbp+0A0h+var_120]
0x18000ca63  jb      loc_18000C9A9
0x18000ca69  cmp     [rbp+0A0h+var_110], 0
0x18000ca6d  jz      short loc_18000CAAC
0x18000ca6f  lea     rdx, [rbp+0A0h+var_80]; struct _MINIDUMP_MEMORY_INFO *
0x18000ca73  mov     rcx, r10; struct _MINIDUMP_STATE *
0x18000ca76  call    ?FilterVmRegion@@YAHPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_MEMORY_INFO@@@Z; FilterVmRegion(_MINIDUMP_STATE *,_MINIDUMP_MEMORY_INFO *)
0x18000ca7b  mov     [rbp+0A0h+var_110], eax
0x18000ca7e  mov     rbx, [rbp+0A0h+var_80.RegionSize]
0x18000ca82  test    rbx, rbx
0x18000ca85  jnz     short loc_18000CA99
0x18000ca87  mov     r10, [rsp+1A0h+var_140]
0x18000ca8c  mov     rdx, [rbp+0A0h+var_118]
0x18000ca90  mov     rcx, [rbp+0A0h+var_120]
0x18000ca94  jmp     loc_18000C9A9
0x18000ca99  mov     r13, [rbp+0A0h+var_80.BaseAddress]
0x18000ca9d  lea     r14, [rbx+r13]
0x18000caa1  mov     r10, [rsp+1A0h+var_140]
0x18000caa6  mov     r9d, 10000h
0x18000caac  xor     esi, esi
0x18000caae  test    r15d, r15d
0x18000cab1  jz      short loc_18000CACD
0x18000cab3  mov     r8, [rsp+1A0h+var_130]
0x18000cab8  lea     rcx, [rsi+rsi*4]
0x18000cabc  cmp     [r8+rcx*4], r13
0x18000cac0  jz      loc_18000CB4D
0x18000cac6  inc     esi
0x18000cac8  cmp     esi, r15d
0x18000cacb  jb      short loc_18000CAB8
0x18000cacd  mov     [rbp+0A0h+var_C0], rbx
0x18000cad1  mov     rcx, rbx
0x18000cad4  mov     rax, rbx
0x18000cad7  test    rax, rax
0x18000cada  jz      loc_18000CC12
0x18000cae0  cmp     rbx, r9
0x18000cae3  cmova   ebx, r9d
0x18000cae7  mov     r15d, 5
0x18000caed  mov     rdx, [rbp+0A0h+var_B8]
0x18000caf1  add     rdx, 1DB8h
0x18000caf8  mov     [rbp+0A0h+var_D8], rdx
0x18000cafc  mov     rcx, [r10+10h]
0x18000cb00  mov     rax, [rcx]
  ... truncated ...
```
