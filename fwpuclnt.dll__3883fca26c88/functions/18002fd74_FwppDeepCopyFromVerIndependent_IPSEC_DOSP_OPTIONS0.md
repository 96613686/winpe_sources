# FwppDeepCopyFromVerIndependent_IPSEC_DOSP_OPTIONS0

- ea: `0x18002fd74`
- end: `0x18003000b`
- name: `FwppDeepCopyFromVerIndependent_IPSEC_DOSP_OPTIONS0`
- size: `663`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180022b50`

## callees

- `0x180007e38`
- `0x18000d870`
- `0x18000ddd0`
- `0x180011500`
- `0x180025440`
- `0x18002cde4`
- `0x18002fd74`
- `0x180036fa8`

## string_xrefs

- `0x18002ffce`: `FwppDeepCopyFromVerIndependent_IPSEC_DOSP_FLAGS`
- `0x18002ffe6`: `FwppDeepCopyFromVerIndependent_IPSEC_DOSP_FLAGS`
- `0x18002ffa5`: `FwppDeepCopyFromVerIndependent_IPSEC_DOSP_OPTIONS0`
- `0x18002fffd`: `FwppDeepCopyFromVerIndependent_IPSEC_DOSP_OPTIONS0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_IPSEC_DOSP_OPTIONS0(__int64 a1, _DWORD *a2)
{
  __int64 v4; // rbx
  _DWORD *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v10; // rax

  if ( !a1 || !a2 )
  {
    v8 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyFromVerIndependent_IPSEC_DOSP_OPTIONS0", 3223453724LL);
LABEL_29:
    v4 = v8;
    if ( !v8 )
      return v4;
    goto LABEL_30;
  }
  v4 = ((__int64 (*)(void))FwppDeepCopyFromVerIndependent_UINT32)();
  if ( !v4 )
  {
    v4 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 4, a2 + 1);
    if ( !v4 )
    {
      v4 = FwppDeepCopyFromVerIndependent_UINT8(a1 + 8, a2 + 2);
      if ( !v4 )
      {
        v4 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 12, a2 + 3);
        if ( !v4 )
        {
          v4 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 16, a2 + 4);
          if ( !v4 )
          {
            v4 = FwppDeepCopyFromVerIndependent_UINT8(a1 + 20, a2 + 5);
            if ( !v4 )
            {
              v4 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 24, a2 + 6);
              if ( !v4 )
              {
                v4 = FwppDeepCopyFromVerIndependent_UINT8(a1 + 28, a2 + 7);
                if ( !v4 )
                {
                  v4 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 32, a2 + 8);
                  if ( !v4 )
                  {
                    v4 = FwppDeepCopyFromVerIndependent_UINT8(a1 + 36, a2 + 9);
                    if ( !v4 )
                    {
                      v4 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 40, a2 + 10);
                      if ( !v4 )
                      {
                        v4 = FwppDeepCopyFromVerIndependent_UINT8(a1 + 44, a2 + 11);
                        if ( !v4 )
                        {
                          v4 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 48, a2 + 12);
                          if ( !v4 )
                          {
                            v4 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 52, a2 + 13);
                            if ( !v4 )
                            {
                              v4 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 56, a2 + 14);
                              if ( !v4 )
                              {
                                if ( a1 == -60 || (v5 = a2 + 15, a2 == (_DWORD *)-60LL) )
                                {
                                  v10 = WfpReportSysErrorAsNtStatus(
                                          v5,
                                          "FwppDeepCopyFromVerIndependent_IPSEC_DOSP_FLAGS",
                                          3223453724LL);
                                  v4 = v10;
                                  if ( v10 )
                                  {
                                    WfpReportError(v10, "FwppDeepCopyFromVerIndependent_IPSEC_DOSP_FLAGS");
                                    goto LABEL_30;
                                  }
                                }
                                else
                                {
                                  *v5 = *(_DWORD *)(a1 + 60);
                                }
                                v6 = *(_QWORD *)(a1 + 72);
                                if ( v6 )
                                {
                                  v4 = FwppArrayAllocAndDeepCopyFromVerIndependent_UINT64(
                                         v6,
                                         *(unsigned int *)(a1 + 64),
                                         a2 + 18);
                                  if ( v4 )
                                    goto LABEL_30;
                                  a2[16] = *(_DWORD *)(a1 + 64);
                                }
                                v7 = *(_QWORD *)(a1 + 88);
                                if ( v7 )
                                {
                                  v4 = FwppArrayAllocAndDeepCopyFromVerIndependent_UINT64(
                                         v7,
                                         *(unsigned int *)(a1 + 80),
                                         a2 + 22);
                                  if ( v4 )
                                    goto LABEL_30;
                                  a2[20] = *(_DWORD *)(a1 + 80);
                                }
                                v4 = FwppDeepCopyFromVerIndependent_FWP_V6_ADDR_AND_MASK(a1 + 96, a2 + 24);
                                if ( !v4 )
                                {
                                  v8 = FwppDeepCopyFromVerIndependent_FWP_V6_ADDR_AND_MASK(a1 + 113, (char *)a2 + 113);
                                  goto LABEL_29;
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_30:
  FwppDeepFreeContentsOnly_IPSEC_DOSP_OPTIONS0(a2);
  if ( v4 )
    WfpReportError(v4, "FwppDeepCopyFromVerIndependent_IPSEC_DOSP_OPTIONS0");
  return v4;
}

```

## disassembly

```asm
0x18002fd74  mov     [rsp+arg_0], rbx
0x18002fd79  mov     [rsp+arg_8], rsi
0x18002fd7e  push    rdi
0x18002fd7f  sub     rsp, 20h
0x18002fd83  mov     rsi, rdx
0x18002fd86  mov     rdi, rcx
0x18002fd89  test    rcx, rcx
0x18002fd8c  jz      loc_18002FFF7
0x18002fd92  test    rdx, rdx
0x18002fd95  jz      loc_18002FFF7
0x18002fd9b  call    FwppDeepCopyFromVerIndependent_UINT32
0x18002fda0  mov     rbx, rax
0x18002fda3  test    rax, rax
0x18002fda6  jnz     loc_18002FF98
0x18002fdac  lea     rdx, [rsi+4]
0x18002fdb0  lea     rcx, [rdi+4]
0x18002fdb4  call    FwppDeepCopyFromVerIndependent_UINT32
0x18002fdb9  mov     rbx, rax
0x18002fdbc  test    rax, rax
0x18002fdbf  jnz     loc_18002FF98
0x18002fdc5  lea     rdx, [rsi+8]
0x18002fdc9  lea     rcx, [rdi+8]
0x18002fdcd  call    FwppDeepCopyFromVerIndependent_UINT8
0x18002fdd2  mov     rbx, rax
0x18002fdd5  test    rax, rax
0x18002fdd8  jnz     loc_18002FF98
0x18002fdde  lea     rdx, [rsi+0Ch]
0x18002fde2  lea     rcx, [rdi+0Ch]
0x18002fde6  call    FwppDeepCopyFromVerIndependent_UINT32
0x18002fdeb  mov     rbx, rax
0x18002fdee  test    rax, rax
0x18002fdf1  jnz     loc_18002FF98
0x18002fdf7  lea     rdx, [rsi+10h]
0x18002fdfb  lea     rcx, [rdi+10h]
0x18002fdff  call    FwppDeepCopyFromVerIndependent_UINT32
0x18002fe04  mov     rbx, rax
0x18002fe07  test    rax, rax
0x18002fe0a  jnz     loc_18002FF98
0x18002fe10  lea     rdx, [rsi+14h]
0x18002fe14  lea     rcx, [rdi+14h]
0x18002fe18  call    FwppDeepCopyFromVerIndependent_UINT8
0x18002fe1d  mov     rbx, rax
0x18002fe20  test    rax, rax
0x18002fe23  jnz     loc_18002FF98
0x18002fe29  lea     rdx, [rsi+18h]
0x18002fe2d  lea     rcx, [rdi+18h]
0x18002fe31  call    FwppDeepCopyFromVerIndependent_UINT32
0x18002fe36  mov     rbx, rax
0x18002fe39  test    rax, rax
0x18002fe3c  jnz     loc_18002FF98
0x18002fe42  lea     rdx, [rsi+1Ch]
0x18002fe46  lea     rcx, [rdi+1Ch]
0x18002fe4a  call    FwppDeepCopyFromVerIndependent_UINT8
0x18002fe4f  mov     rbx, rax
0x18002fe52  test    rax, rax
0x18002fe55  jnz     loc_18002FF98
0x18002fe5b  lea     rdx, [rsi+20h]
0x18002fe5f  lea     rcx, [rdi+20h]
0x18002fe63  call    FwppDeepCopyFromVerIndependent_UINT32
0x18002fe68  mov     rbx, rax
0x18002fe6b  test    rax, rax
0x18002fe6e  jnz     loc_18002FF98
0x18002fe74  lea     rdx, [rsi+24h]
0x18002fe78  lea     rcx, [rdi+24h]
0x18002fe7c  call    FwppDeepCopyFromVerIndependent_UINT8
0x18002fe81  mov     rbx, rax
0x18002fe84  test    rax, rax
0x18002fe87  jnz     loc_18002FF98
0x18002fe8d  lea     rdx, [rsi+28h]
0x18002fe91  lea     rcx, [rdi+28h]
0x18002fe95  call    FwppDeepCopyFromVerIndependent_UINT32
0x18002fe9a  mov     rbx, rax
0x18002fe9d  test    rax, rax
0x18002fea0  jnz     loc_18002FF98
0x18002fea6  lea     rdx, [rsi+2Ch]
0x18002feaa  lea     rcx, [rdi+2Ch]
0x18002feae  call    FwppDeepCopyFromVerIndependent_UINT8
0x18002feb3  mov     rbx, rax
0x18002feb6  test    rax, rax
0x18002feb9  jnz     loc_18002FF98
0x18002febf  lea     rdx, [rsi+30h]
0x18002fec3  lea     rcx, [rdi+30h]
0x18002fec7  call    FwppDeepCopyFromVerIndependent_UINT32
0x18002fecc  mov     rbx, rax
0x18002fecf  test    rax, rax
0x18002fed2  jnz     loc_18002FF98
0x18002fed8  lea     rdx, [rsi+34h]
0x18002fedc  lea     rcx, [rdi+34h]
0x18002fee0  call    FwppDeepCopyFromVerIndependent_UINT32
0x18002fee5  mov     rbx, rax
0x18002fee8  test    rax, rax
0x18002feeb  jnz     loc_18002FF98
0x18002fef1  lea     rdx, [rsi+38h]
0x18002fef5  lea     rcx, [rdi+38h]
0x18002fef9  call    FwppDeepCopyFromVerIndependent_UINT32
0x18002fefe  mov     rbx, rax
0x18002ff01  test    rax, rax
0x18002ff04  jnz     loc_18002FF98
0x18002ff0a  lea     rax, [rdi+3Ch]
0x18002ff0e  test    rax, rax
0x18002ff11  jz      loc_18002FFC8
0x18002ff17  lea     rcx, [rsi+3Ch]
0x18002ff1b  test    rcx, rcx
0x18002ff1e  jz      loc_18002FFC8
0x18002ff24  mov     eax, [rax]
0x18002ff26  mov     [rcx], eax
0x18002ff28  mov     rcx, [rdi+48h]
0x18002ff2c  test    rcx, rcx
0x18002ff2f  jz      short loc_18002FF4B
0x18002ff31  mov     edx, [rdi+40h]
0x18002ff34  lea     r8, [rsi+48h]
0x18002ff38  call    FwppArrayAllocAndDeepCopyFromVerIndependent_UINT64
0x18002ff3d  mov     rbx, rax
0x18002ff40  test    rax, rax
0x18002ff43  jnz     short loc_18002FF98
0x18002ff45  mov     eax, [rdi+40h]
0x18002ff48  mov     [rsi+40h], eax
0x18002ff4b  mov     rcx, [rdi+58h]
0x18002ff4f  test    rcx, rcx
0x18002ff52  jz      short loc_18002FF6E
0x18002ff54  mov     edx, [rdi+50h]
0x18002ff57  lea     r8, [rsi+58h]
0x18002ff5b  call    FwppArrayAllocAndDeepCopyFromVerIndependent_UINT64
0x18002ff60  mov     rbx, rax
0x18002ff63  test    rax, rax
0x18002ff66  jnz     short loc_18002FF98
0x18002ff68  mov     eax, [rdi+50h]
0x18002ff6b  mov     [rsi+50h], eax
0x18002ff6e  lea     rdx, [rsi+60h]
0x18002ff72  lea     rcx, [rdi+60h]
0x18002ff76  call    FwppDeepCopyFromVerIndependent_FWP_V6_ADDR_AND_MASK
0x18002ff7b  mov     rbx, rax
0x18002ff7e  test    rax, rax
0x18002ff81  jnz     short loc_18002FF98
0x18002ff83  lea     rdx, [rsi+71h]
0x18002ff87  lea     rcx, [rdi+71h]
0x18002ff8b  call    FwppDeepCopyFromVerIndependent_FWP_V6_ADDR_AND_MASK
0x18002ff90  mov     rbx, rax
0x18002ff93  test    rax, rax
0x18002ff96  jz      short loc_18002FFB4
0x18002ff98  mov     rcx, rsi
0x18002ff9b  call    FwppDeepFreeContentsOnly_IPSEC_DOSP_OPTIONS0
0x18002ffa0  test    rbx, rbx
0x18002ffa3  jz      short loc_18002FFB4
0x18002ffa5  lea     rdx, aFwppdeepcopyfr_96; "FwppDeepCopyFromVerIndependent_IPSEC_DO"...
0x18002ffac  mov     rcx, rbx
0x18002ffaf  call    WfpReportError
0x18002ffb4  mov     rsi, [rsp+28h+arg_8]
0x18002ffb9  mov     rax, rbx
0x18002ffbc  mov     rbx, [rsp+28h+arg_0]
0x18002ffc1  add     rsp, 20h
0x18002ffc5  pop     rdi
0x18002ffc6  retn
0x18002ffc8  mov     r8d, 0C022001Ch
0x18002ffce  lea     rdx, aFwppdeepcopyfr_131; "FwppDeepCopyFromVerIndependent_IPSEC_DO"...
0x18002ffd5  call    WfpReportSysErrorAsNtStatus
0x18002ffda  mov     rbx, rax
0x18002ffdd  test    rax, rax
0x18002ffe0  jz      loc_18002FF28
0x18002ffe6  lea     rdx, aFwppdeepcopyfr_131; "FwppDeepCopyFromVerIndependent_IPSEC_DO"...
0x18002ffed  mov     rcx, rax
0x18002fff0  call    WfpReportError
0x18002fff5  jmp     short loc_18002FF98
0x18002fff7  mov     r8d, 0C022001Ch
0x18002fffd  lea     rdx, aFwppdeepcopyfr_96; "FwppDeepCopyFromVerIndependent_IPSEC_DO"...
0x180030004  call    WfpReportSysErrorAsNtStatus
0x180030009  jmp     short loc_18002FF90
```
