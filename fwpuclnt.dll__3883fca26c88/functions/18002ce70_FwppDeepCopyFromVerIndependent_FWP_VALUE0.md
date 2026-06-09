# FwppDeepCopyFromVerIndependent_FWP_VALUE0

- ea: `0x18002ce70`
- end: `0x18002d0d1`
- name: `FwppDeepCopyFromVerIndependent_FWP_VALUE0`
- size: `609`
- prototype: ``
- caller_count: `3`
- callee_count: `21`
- tags: `authz_impersonation`

## callers

- `0x180029cd8`
- `0x180029e74`
- `0x18002cc14`

## callees

- `0x18000648c`
- `0x1800071fc`
- `0x180007e38`
- `0x18000d870`
- `0x18000d9d0`
- `0x18000ddd0`
- `0x1800101a8`
- `0x180010df0`
- `0x180011500`
- `0x180021d90`
- `0x180021e14`
- `0x180021f20`
- `0x180022940`
- `0x18002347c`
- `0x1800234fc`
- `0x18002cb6c`
- `0x18002ce70`
- `0x18002f640`
- `0x18002f694`
- `0x18002f73c`
- `0x180031dd0`

## string_xrefs

- `0x18002cf18`: `FwppDeepCopyFromVerIndependent_FWP_VALUE0`
- `0x18002d0c0`: `FwppDeepCopyFromVerIndependent_FWP_VALUE0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_FWP_VALUE0(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  __int64 v14; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // edx
  int v20; // edx
  int v21; // edx
  int v22; // edx
  int v23; // edx
  int v24; // edx
  int v25; // edx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  void *v30; // rcx
  __int64 v31; // rcx

  if ( !a1 || !a2 )
  {
    v14 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyFromVerIndependent_FWP_VALUE0", 3223453724LL);
    goto LABEL_16;
  }
  v4 = FwppDeepCopyFromVerIndependent_FWP_DATA_TYPE();
  if ( !v4 )
  {
    v5 = *(_DWORD *)a1;
    if ( *(int *)a1 <= 10 )
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
      goto LABEL_16;
    }
    v19 = v5 - 11;
    if ( !v19 )
    {
      v31 = *(_QWORD *)(a1 + 8);
      if ( !v31 )
        return v4;
      v14 = FwppAllocAndDeepCopyFromVerIndependent_FWP_BYTE_ARRAY16(v31, a2 + 8);
      goto LABEL_16;
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
        goto LABEL_16;
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
          goto LABEL_16;
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
          goto LABEL_16;
        }
      }
    }
    v28 = *(_QWORD *)(a1 + 8);
    if ( !v28 )
      return v4;
    v14 = FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_BLOB(v28, a2 + 8);
LABEL_16:
    v4 = v14;
    if ( !v14 )
      return v4;
  }
  FwppDeepFreeContentsOnly_FWP_VALUE0(a2);
  if ( v4 )
    WfpReportError(v4, "FwppDeepCopyFromVerIndependent_FWP_VALUE0");
  return v4;
}

```

## disassembly

```asm
0x18002ce70  mov     [rsp+arg_0], rbx
0x18002ce75  mov     [rsp+arg_8], rsi
0x18002ce7a  push    rdi
0x18002ce7b  sub     rsp, 20h
0x18002ce7f  mov     rsi, rdx
0x18002ce82  mov     rdi, rcx
0x18002ce85  test    rcx, rcx
0x18002ce88  jz      loc_18002D0BA
0x18002ce8e  test    rdx, rdx
0x18002ce91  jz      loc_18002D0BA
0x18002ce97  call    FwppDeepCopyFromVerIndependent_FWP_DATA_TYPE
0x18002ce9c  mov     rbx, rax
0x18002ce9f  test    rax, rax
0x18002cea2  jnz     short loc_18002CF0B
0x18002cea4  mov     edx, [rdi]
0x18002cea6  cmp     edx, 0Ah
0x18002cea9  jg      loc_18002CFE4
0x18002ceaf  jz      loc_18002CFC9
0x18002ceb5  sub     edx, 1
0x18002ceb8  jz      loc_18002CFB7
0x18002cebe  sub     edx, 1
0x18002cec1  jz      loc_18002CFA5
0x18002cec7  sub     edx, 1
0x18002ceca  jz      loc_18002CF93
0x18002ced0  sub     edx, 1
0x18002ced3  jz      loc_18002CF7C
0x18002ced9  sub     edx, 1
0x18002cedc  jz      loc_18002CF6D
0x18002cee2  sub     edx, 1
0x18002cee5  jz      short loc_18002CF5E
0x18002cee7  sub     edx, 1
0x18002ceea  jz      short loc_18002CF4F
0x18002ceec  sub     edx, 1
0x18002ceef  jz      short loc_18002CF3B
0x18002cef1  cmp     edx, 1
0x18002cef4  jnz     short loc_18002CF27
0x18002cef6  lea     rdx, [rsi+8]
0x18002cefa  lea     rcx, [rdi+8]
0x18002cefe  call    FwppDeepCopyFromVerIndependent_float
0x18002cf03  mov     rbx, rax
0x18002cf06  test    rax, rax
0x18002cf09  jz      short loc_18002CF27
0x18002cf0b  mov     rcx, rsi
0x18002cf0e  call    FwppDeepFreeContentsOnly_FWP_VALUE0
0x18002cf13  test    rbx, rbx
0x18002cf16  jz      short loc_18002CF27
0x18002cf18  lea     rdx, aFwppdeepcopyfr_112; "FwppDeepCopyFromVerIndependent_FWP_VALU"...
0x18002cf1f  mov     rcx, rbx
0x18002cf22  call    WfpReportError
0x18002cf27  mov     rsi, [rsp+28h+arg_8]
0x18002cf2c  mov     rax, rbx
0x18002cf2f  mov     rbx, [rsp+28h+arg_0]
0x18002cf34  add     rsp, 20h
0x18002cf38  pop     rdi
0x18002cf39  retn
0x18002cf3b  mov     rcx, [rdi+8]
0x18002cf3f  test    rcx, rcx
0x18002cf42  jz      short loc_18002CF27
0x18002cf44  lea     rdx, [rsi+8]
0x18002cf48  call    FwppAllocAndDeepCopyFromVerIndependent_INT64
0x18002cf4d  jmp     short loc_18002CF03
0x18002cf4f  lea     rdx, [rsi+8]
0x18002cf53  lea     rcx, [rdi+8]
0x18002cf57  call    FwppDeepCopyFromVerIndependent_INT32
0x18002cf5c  jmp     short loc_18002CF03
0x18002cf5e  lea     rdx, [rsi+8]
0x18002cf62  lea     rcx, [rdi+8]
0x18002cf66  call    FwppDeepCopyFromVerIndependent_INT16
0x18002cf6b  jmp     short loc_18002CF03
0x18002cf6d  lea     rdx, [rsi+8]
0x18002cf71  lea     rcx, [rdi+8]
0x18002cf75  call    FwppDeepCopyFromVerIndependent_INT8
0x18002cf7a  jmp     short loc_18002CF03
0x18002cf7c  mov     rcx, [rdi+8]
0x18002cf80  test    rcx, rcx
0x18002cf83  jz      short loc_18002CF27
0x18002cf85  lea     rdx, [rsi+8]
0x18002cf89  call    FwppAllocAndDeepCopyFromVerIndependent_UINT64
0x18002cf8e  jmp     loc_18002CF03
0x18002cf93  lea     rdx, [rsi+8]
0x18002cf97  lea     rcx, [rdi+8]
0x18002cf9b  call    FwppDeepCopyFromVerIndependent_UINT32
0x18002cfa0  jmp     loc_18002CF03
0x18002cfa5  lea     rdx, [rsi+8]
0x18002cfa9  lea     rcx, [rdi+8]
0x18002cfad  call    FwppDeepCopyFromVerIndependent_UINT16
0x18002cfb2  jmp     loc_18002CF03
0x18002cfb7  lea     rdx, [rsi+8]
0x18002cfbb  lea     rcx, [rdi+8]
0x18002cfbf  call    FwppDeepCopyFromVerIndependent_UINT8
0x18002cfc4  jmp     loc_18002CF03
0x18002cfc9  mov     rcx, [rdi+8]
0x18002cfcd  test    rcx, rcx
0x18002cfd0  jz      loc_18002CF27
0x18002cfd6  lea     rdx, [rsi+8]
0x18002cfda  call    FwppAllocAndDeepCopyFromVerIndependent_double
0x18002cfdf  jmp     loc_18002CF03
0x18002cfe4  sub     edx, 0Bh
0x18002cfe7  jz      loc_18002D09F
0x18002cfed  sub     edx, 1
0x18002cff0  jz      short loc_18002D04E
0x18002cff2  sub     edx, 1
0x18002cff5  jz      loc_18002D084
0x18002cffb  sub     edx, 1
0x18002cffe  jz      short loc_18002D04E
0x18002d000  sub     edx, 1
0x18002d003  jz      short loc_18002D069
0x18002d005  sub     edx, 1
0x18002d008  jz      short loc_18002D04E
0x18002d00a  sub     edx, 1
0x18002d00d  jz      short loc_18002D033
0x18002d00f  cmp     edx, 1
0x18002d012  jnz     loc_18002CF27
0x18002d018  mov     rcx, [rdi+8]
0x18002d01c  test    rcx, rcx
0x18002d01f  jz      loc_18002CF27
0x18002d025  lea     rdx, [rsi+8]
0x18002d029  call    FwppAllocAndDeepCopyFromVerIndependent_FWP_BYTE_ARRAY6
0x18002d02e  jmp     loc_18002CF03
0x18002d033  mov     rcx, [rdi+8]
0x18002d037  test    rcx, rcx
0x18002d03a  jz      loc_18002CF27
0x18002d040  lea     rdx, [rsi+8]
0x18002d044  call    FwppAllocAndDeepCopyToVerIndependent_WSTR
0x18002d049  jmp     loc_18002CF03
0x18002d04e  mov     rcx, [rdi+8]
0x18002d052  test    rcx, rcx
0x18002d055  jz      loc_18002CF27
0x18002d05b  lea     rdx, [rsi+8]
0x18002d05f  call    FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x18002d064  jmp     loc_18002CF03
0x18002d069  mov     rcx, [rdi+8]
0x18002d06d  test    rcx, rcx
0x18002d070  jz      loc_18002CF27
0x18002d076  lea     rdx, [rsi+8]
0x18002d07a  call    FwppAllocAndDeepCopyFromVerIndependent_FWP_TOKEN_INFORMATION
0x18002d07f  jmp     loc_18002CF03
0x18002d084  mov     rcx, [rdi+8]; SourceSid
0x18002d088  test    rcx, rcx
0x18002d08b  jz      loc_18002CF27
0x18002d091  lea     rdx, [rsi+8]
0x18002d095  call    FwppAllocAndDeepCopyToVerIndependent_SID
0x18002d09a  jmp     loc_18002CF03
0x18002d09f  mov     rcx, [rdi+8]
0x18002d0a3  test    rcx, rcx
0x18002d0a6  jz      loc_18002CF27
0x18002d0ac  lea     rdx, [rsi+8]
0x18002d0b0  call    FwppAllocAndDeepCopyFromVerIndependent_FWP_BYTE_ARRAY16
0x18002d0b5  jmp     loc_18002CF03
0x18002d0ba  mov     r8d, 0C022001Ch
0x18002d0c0  lea     rdx, aFwppdeepcopyfr_112; "FwppDeepCopyFromVerIndependent_FWP_VALU"...
0x18002d0c7  call    WfpReportSysErrorAsNtStatus
0x18002d0cc  jmp     loc_18002CF03
```
