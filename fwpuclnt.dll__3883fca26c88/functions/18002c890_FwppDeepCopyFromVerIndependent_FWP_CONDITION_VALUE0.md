# FwppDeepCopyFromVerIndependent_FWP_CONDITION_VALUE0

- ea: `0x18002c890`
- end: `0x18002cb66`
- name: `FwppDeepCopyFromVerIndependent_FWP_CONDITION_VALUE0`
- size: `726`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `authz_impersonation`

## callers

- `0x18002bc5c`
- `0x18002bd94`

## callees

- `0x18000648c`
- `0x1800071fc`
- `0x180007e38`
- `0x18000d870`
- `0x18000d9d0`
- `0x18000ddd0`
- `0x1800101a8`
- `0x180011500`
- `0x180021d90`
- `0x180021e14`
- `0x180021e98`
- `0x180021f20`
- `0x180021fa8`
- `0x180022028`
- `0x180022940`
- `0x18002347c`
- `0x1800234fc`
- `0x18002c890`
- `0x18002cb6c`
- `0x18002f640`
- `0x18002f694`
- `0x18002f73c`
- `0x180031dd0`
- `0x1800367f4`

## string_xrefs

- `0x18002c94b`: `FwppDeepCopyFromVerIndependent_FWP_CONDITION_VALUE0`
- `0x18002cb55`: `FwppDeepCopyFromVerIndependent_FWP_CONDITION_VALUE0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_FWP_CONDITION_VALUE0(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  __int64 v14; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  void *v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  int v33; // ecx
  __int64 v34; // rcx
  __int64 v35; // rcx

  if ( !a1 || !a2 )
  {
    v14 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyFromVerIndependent_FWP_CONDITION_VALUE0", 3223453724LL);
    goto LABEL_18;
  }
  v4 = FwppDeepCopyFromVerIndependent_FWP_DATA_TYPE();
  if ( !v4 )
  {
    v5 = *(_DWORD *)a1;
    if ( *(int *)a1 > 256 )
    {
      v33 = v5 - 257;
      if ( v33 )
      {
        if ( v33 != 1 )
          return v4;
        v34 = *(_QWORD *)(a1 + 8);
        if ( !v34 )
          return v4;
        v14 = FwppAllocAndDeepCopyFromVerIndependent_FWP_RANGE0(v34, a2 + 8);
      }
      else
      {
        v35 = *(_QWORD *)(a1 + 8);
        if ( !v35 )
          return v4;
        v14 = FwppAllocAndDeepCopyFromVerIndependent_FWP_V6_ADDR_AND_MASK(v35, a2 + 8);
      }
      goto LABEL_18;
    }
    if ( v5 == 256 )
    {
      v32 = *(_QWORD *)(a1 + 8);
      if ( !v32 )
        return v4;
      v14 = FwppAllocAndDeepCopyFromVerIndependent_FWP_V4_ADDR_AND_MASK(v32, a2 + 8);
      goto LABEL_18;
    }
    if ( v5 <= 10 )
    {
      if ( v5 == 10 )
      {
        v18 = *(_QWORD *)(a1 + 8);
        if ( !v18 )
          return v4;
        v14 = FwppAllocAndDeepCopyFromVerIndependent_double(v18, a2 + 8);
      }
      else
      {
        v6 = v5 - 1;
        if ( v6 )
        {
          v7 = v6 - 1;
          if ( v7 )
          {
            v8 = v7 - 1;
            if ( v8 )
            {
              v9 = v8 - 1;
              if ( v9 )
              {
                v10 = v9 - 1;
                if ( v10 )
                {
                  v11 = v10 - 1;
                  if ( v11 )
                  {
                    v12 = v11 - 1;
                    if ( v12 )
                    {
                      v13 = v12 - 1;
                      if ( v13 )
                      {
                        if ( v13 != 1 )
                          return v4;
                        v14 = FwppDeepCopyFromVerIndependent_float(a1 + 8, a2 + 8);
                      }
                      else
                      {
                        v16 = *(_QWORD *)(a1 + 8);
                        if ( !v16 )
                          return v4;
                        v14 = FwppAllocAndDeepCopyFromVerIndependent_INT64(v16, a2 + 8);
                      }
                    }
                    else
                    {
                      v14 = FwppDeepCopyFromVerIndependent_INT32(a1 + 8, a2 + 8);
                    }
                  }
                  else
                  {
                    v14 = FwppDeepCopyFromVerIndependent_INT16(a1 + 8, a2 + 8);
                  }
                }
                else
                {
                  v14 = FwppDeepCopyFromVerIndependent_INT8(a1 + 8, a2 + 8);
                }
              }
              else
              {
                v17 = *(_QWORD *)(a1 + 8);
                if ( !v17 )
                  return v4;
                v14 = FwppAllocAndDeepCopyFromVerIndependent_UINT64(v17, a2 + 8);
              }
            }
            else
            {
              v14 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 8, a2 + 8);
            }
          }
          else
          {
            v14 = FwppDeepCopyFromVerIndependent_UINT16(a1 + 8, a2 + 8);
          }
        }
        else
        {
          v14 = FwppDeepCopyFromVerIndependent_UINT8(a1 + 8, a2 + 8);
        }
      }
      goto LABEL_18;
    }
    v19 = v5 - 11;
    if ( !v19 )
    {
      v31 = *(_QWORD *)(a1 + 8);
      if ( !v31 )
        return v4;
      v14 = FwppAllocAndDeepCopyFromVerIndependent_FWP_BYTE_ARRAY16(v31, a2 + 8);
      goto LABEL_18;
    }
    v20 = v19 - 1;
    if ( v20 )
    {
      v21 = v20 - 1;
      if ( !v21 )
      {
        v30 = *(void **)(a1 + 8);
        if ( !v30 )
          return v4;
        v14 = FwppAllocAndDeepCopyToVerIndependent_SID(v30, (_QWORD *)(a2 + 8));
        goto LABEL_18;
      }
      v22 = v21 - 1;
      if ( v22 )
      {
        v23 = v22 - 1;
        if ( !v23 )
        {
          v29 = *(_QWORD *)(a1 + 8);
          if ( !v29 )
            return v4;
          v14 = FwppAllocAndDeepCopyFromVerIndependent_FWP_TOKEN_INFORMATION(v29, a2 + 8);
          goto LABEL_18;
        }
        v24 = v23 - 1;
        if ( v24 )
        {
          v25 = v24 - 1;
          if ( v25 )
          {
            if ( v25 != 1 )
              return v4;
            v26 = *(_QWORD *)(a1 + 8);
            if ( !v26 )
              return v4;
            v14 = FwppAllocAndDeepCopyFromVerIndependent_FWP_BYTE_ARRAY6(v26, a2 + 8);
          }
          else
          {
            v27 = *(_QWORD *)(a1 + 8);
            if ( !v27 )
              return v4;
            v14 = FwppAllocAndDeepCopyToVerIndependent_WSTR(v27, a2 + 8);
          }
          goto LABEL_18;
        }
      }
    }
    v28 = *(_QWORD *)(a1 + 8);
    if ( !v28 )
      return v4;
    v14 = FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_BLOB(v28, a2 + 8);
LABEL_18:
    v4 = v14;
    if ( !v14 )
      return v4;
  }
  FwppDeepFreeContentsOnly_FWP_CONDITION_VALUE0(a2);
  if ( v4 )
    WfpReportError(v4, "FwppDeepCopyFromVerIndependent_FWP_CONDITION_VALUE0");
  return v4;
}

```

## disassembly

```asm
0x18002c890  mov     [rsp+arg_0], rbx
0x18002c895  mov     [rsp+arg_8], rsi
0x18002c89a  push    rdi
0x18002c89b  sub     rsp, 20h
0x18002c89f  mov     rsi, rdx
0x18002c8a2  mov     rdi, rcx
0x18002c8a5  test    rcx, rcx
0x18002c8a8  jz      loc_18002CB4F
0x18002c8ae  test    rdx, rdx
0x18002c8b1  jz      loc_18002CB4F
0x18002c8b7  call    FwppDeepCopyFromVerIndependent_FWP_DATA_TYPE
0x18002c8bc  mov     rbx, rax
0x18002c8bf  test    rax, rax
0x18002c8c2  jnz     short loc_18002C93E
0x18002c8c4  mov     ecx, [rdi]
0x18002c8c6  mov     eax, 100h
0x18002c8cb  cmp     ecx, eax
0x18002c8cd  jg      loc_18002CB08
0x18002c8d3  jz      loc_18002CAED
0x18002c8d9  cmp     ecx, 0Ah
0x18002c8dc  jg      loc_18002CA17
0x18002c8e2  jz      loc_18002C9FC
0x18002c8e8  sub     ecx, 1
0x18002c8eb  jz      loc_18002C9EA
0x18002c8f1  sub     ecx, 1
0x18002c8f4  jz      loc_18002C9D8
0x18002c8fa  sub     ecx, 1
0x18002c8fd  jz      loc_18002C9C6
0x18002c903  sub     ecx, 1
0x18002c906  jz      loc_18002C9AF
0x18002c90c  sub     ecx, 1
0x18002c90f  jz      loc_18002C9A0
0x18002c915  sub     ecx, 1
0x18002c918  jz      short loc_18002C991
0x18002c91a  sub     ecx, 1
0x18002c91d  jz      short loc_18002C982
0x18002c91f  sub     ecx, 1
0x18002c922  jz      short loc_18002C96E
0x18002c924  cmp     ecx, 1
0x18002c927  jnz     short loc_18002C95A
0x18002c929  lea     rdx, [rsi+8]
0x18002c92d  lea     rcx, [rdi+8]
0x18002c931  call    FwppDeepCopyFromVerIndependent_float
0x18002c936  mov     rbx, rax
0x18002c939  test    rax, rax
0x18002c93c  jz      short loc_18002C95A
0x18002c93e  mov     rcx, rsi
0x18002c941  call    FwppDeepFreeContentsOnly_FWP_CONDITION_VALUE0
0x18002c946  test    rbx, rbx
0x18002c949  jz      short loc_18002C95A
0x18002c94b  lea     rdx, aFwppdeepcopyfr_39; "FwppDeepCopyFromVerIndependent_FWP_COND"...
0x18002c952  mov     rcx, rbx
0x18002c955  call    WfpReportError
0x18002c95a  mov     rsi, [rsp+28h+arg_8]
0x18002c95f  mov     rax, rbx
0x18002c962  mov     rbx, [rsp+28h+arg_0]
0x18002c967  add     rsp, 20h
0x18002c96b  pop     rdi
0x18002c96c  retn
0x18002c96e  mov     rcx, [rdi+8]
0x18002c972  test    rcx, rcx
0x18002c975  jz      short loc_18002C95A
0x18002c977  lea     rdx, [rsi+8]
0x18002c97b  call    FwppAllocAndDeepCopyFromVerIndependent_INT64
0x18002c980  jmp     short loc_18002C936
0x18002c982  lea     rdx, [rsi+8]
0x18002c986  lea     rcx, [rdi+8]
0x18002c98a  call    FwppDeepCopyFromVerIndependent_INT32
0x18002c98f  jmp     short loc_18002C936
0x18002c991  lea     rdx, [rsi+8]
0x18002c995  lea     rcx, [rdi+8]
0x18002c999  call    FwppDeepCopyFromVerIndependent_INT16
0x18002c99e  jmp     short loc_18002C936
0x18002c9a0  lea     rdx, [rsi+8]
0x18002c9a4  lea     rcx, [rdi+8]
0x18002c9a8  call    FwppDeepCopyFromVerIndependent_INT8
0x18002c9ad  jmp     short loc_18002C936
0x18002c9af  mov     rcx, [rdi+8]
0x18002c9b3  test    rcx, rcx
0x18002c9b6  jz      short loc_18002C95A
0x18002c9b8  lea     rdx, [rsi+8]
0x18002c9bc  call    FwppAllocAndDeepCopyFromVerIndependent_UINT64
0x18002c9c1  jmp     loc_18002C936
0x18002c9c6  lea     rdx, [rsi+8]
0x18002c9ca  lea     rcx, [rdi+8]
0x18002c9ce  call    FwppDeepCopyFromVerIndependent_UINT32
0x18002c9d3  jmp     loc_18002C936
0x18002c9d8  lea     rdx, [rsi+8]
0x18002c9dc  lea     rcx, [rdi+8]
0x18002c9e0  call    FwppDeepCopyFromVerIndependent_UINT16
0x18002c9e5  jmp     loc_18002C936
0x18002c9ea  lea     rdx, [rsi+8]
0x18002c9ee  lea     rcx, [rdi+8]
0x18002c9f2  call    FwppDeepCopyFromVerIndependent_UINT8
0x18002c9f7  jmp     loc_18002C936
0x18002c9fc  mov     rcx, [rdi+8]
0x18002ca00  test    rcx, rcx
0x18002ca03  jz      loc_18002C95A
0x18002ca09  lea     rdx, [rsi+8]
0x18002ca0d  call    FwppAllocAndDeepCopyFromVerIndependent_double
0x18002ca12  jmp     loc_18002C936
0x18002ca17  sub     ecx, 0Bh
0x18002ca1a  jz      loc_18002CAD2
0x18002ca20  sub     ecx, 1
0x18002ca23  jz      short loc_18002CA81
0x18002ca25  sub     ecx, 1
0x18002ca28  jz      loc_18002CAB7
0x18002ca2e  sub     ecx, 1
0x18002ca31  jz      short loc_18002CA81
0x18002ca33  sub     ecx, 1
0x18002ca36  jz      short loc_18002CA9C
0x18002ca38  sub     ecx, 1
0x18002ca3b  jz      short loc_18002CA81
0x18002ca3d  sub     ecx, 1
0x18002ca40  jz      short loc_18002CA66
0x18002ca42  cmp     ecx, 1
0x18002ca45  jnz     loc_18002C95A
0x18002ca4b  mov     rcx, [rdi+8]
0x18002ca4f  test    rcx, rcx
0x18002ca52  jz      loc_18002C95A
0x18002ca58  lea     rdx, [rsi+8]
0x18002ca5c  call    FwppAllocAndDeepCopyFromVerIndependent_FWP_BYTE_ARRAY6
0x18002ca61  jmp     loc_18002C936
0x18002ca66  mov     rcx, [rdi+8]
0x18002ca6a  test    rcx, rcx
0x18002ca6d  jz      loc_18002C95A
0x18002ca73  lea     rdx, [rsi+8]
0x18002ca77  call    FwppAllocAndDeepCopyToVerIndependent_WSTR
0x18002ca7c  jmp     loc_18002C936
0x18002ca81  mov     rcx, [rdi+8]
0x18002ca85  test    rcx, rcx
0x18002ca88  jz      loc_18002C95A
0x18002ca8e  lea     rdx, [rsi+8]
0x18002ca92  call    FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x18002ca97  jmp     loc_18002C936
0x18002ca9c  mov     rcx, [rdi+8]
0x18002caa0  test    rcx, rcx
0x18002caa3  jz      loc_18002C95A
0x18002caa9  lea     rdx, [rsi+8]
0x18002caad  call    FwppAllocAndDeepCopyFromVerIndependent_FWP_TOKEN_INFORMATION
0x18002cab2  jmp     loc_18002C936
0x18002cab7  mov     rcx, [rdi+8]; SourceSid
0x18002cabb  test    rcx, rcx
0x18002cabe  jz      loc_18002C95A
0x18002cac4  lea     rdx, [rsi+8]
0x18002cac8  call    FwppAllocAndDeepCopyToVerIndependent_SID
0x18002cacd  jmp     loc_18002C936
0x18002cad2  mov     rcx, [rdi+8]
0x18002cad6  test    rcx, rcx
0x18002cad9  jz      loc_18002C95A
0x18002cadf  lea     rdx, [rsi+8]
0x18002cae3  call    FwppAllocAndDeepCopyFromVerIndependent_FWP_BYTE_ARRAY16
0x18002cae8  jmp     loc_18002C936
0x18002caed  mov     rcx, [rdi+8]
0x18002caf1  test    rcx, rcx
0x18002caf4  jz      loc_18002C95A
0x18002cafa  lea     rdx, [rsi+8]
0x18002cafe  call    FwppAllocAndDeepCopyFromVerIndependent_FWP_V4_ADDR_AND_MASK
0x18002cb03  jmp     loc_18002C936
0x18002cb08  sub     ecx, 101h
0x18002cb0e  jz      short loc_18002CB34
0x18002cb10  cmp     ecx, 1
0x18002cb13  jnz     loc_18002C95A
0x18002cb19  mov     rcx, [rdi+8]
0x18002cb1d  test    rcx, rcx
0x18002cb20  jz      loc_18002C95A
0x18002cb26  lea     rdx, [rsi+8]
0x18002cb2a  call    FwppAllocAndDeepCopyFromVerIndependent_FWP_RANGE0
0x18002cb2f  jmp     loc_18002C936
0x18002cb34  mov     rcx, [rdi+8]
0x18002cb38  test    rcx, rcx
0x18002cb3b  jz      loc_18002C95A
0x18002cb41  lea     rdx, [rsi+8]
0x18002cb45  call    FwppAllocAndDeepCopyFromVerIndependent_FWP_V6_ADDR_AND_MASK
0x18002cb4a  jmp     loc_18002C936
0x18002cb4f  mov     r8d, 0C022001Ch
0x18002cb55  lea     rdx, aFwppdeepcopyfr_39; "FwppDeepCopyFromVerIndependent_FWP_COND"...
0x18002cb5c  call    WfpReportSysErrorAsNtStatus
0x18002cb61  jmp     loc_18002C936
```
