# FwppDeepCopyToVerIndependent_IPSEC_DOSP_OPTIONS0

- ea: `0x1800344d8`
- end: `0x18003476f`
- name: `FwppDeepCopyToVerIndependent_IPSEC_DOSP_OPTIONS0`
- size: `663`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180023c5c`

## callees

- `0x180007e38`
- `0x180011500`
- `0x18002604c`
- `0x1800329e8`
- `0x1800344d8`
- `0x180035d48`
- `0x180035df0`
- `0x180036fa8`

## string_xrefs

- `0x180034732`: `FwppDeepCopyToVerIndependent_IPSEC_DOSP_FLAGS`
- `0x18003474a`: `FwppDeepCopyToVerIndependent_IPSEC_DOSP_FLAGS`
- `0x180034709`: `FwppDeepCopyToVerIndependent_IPSEC_DOSP_OPTIONS0`
- `0x180034761`: `FwppDeepCopyToVerIndependent_IPSEC_DOSP_OPTIONS0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_IPSEC_DOSP_OPTIONS0(__int64 a1, _DWORD *a2)
{
  __int64 v4; // rbx
  _DWORD *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v10; // rax

  if ( !a1 || !a2 )
  {
    v8 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyToVerIndependent_IPSEC_DOSP_OPTIONS0", 3223453724LL);
LABEL_29:
    v4 = v8;
    if ( !v8 )
      return v4;
    goto LABEL_30;
  }
  v4 = FwppDeepCopyToVerIndependent_UINT32(a1, a2);
  if ( !v4 )
  {
    v4 = FwppDeepCopyToVerIndependent_UINT32(a1 + 4, a2 + 1);
    if ( !v4 )
    {
      v4 = FwppDeepCopyToVerIndependent_UINT8(a1 + 8, a2 + 2);
      if ( !v4 )
      {
        v4 = FwppDeepCopyToVerIndependent_UINT32(a1 + 12, a2 + 3);
        if ( !v4 )
        {
          v4 = FwppDeepCopyToVerIndependent_UINT32(a1 + 16, a2 + 4);
          if ( !v4 )
          {
            v4 = FwppDeepCopyToVerIndependent_UINT8(a1 + 20, a2 + 5);
            if ( !v4 )
            {
              v4 = FwppDeepCopyToVerIndependent_UINT32(a1 + 24, a2 + 6);
              if ( !v4 )
              {
                v4 = FwppDeepCopyToVerIndependent_UINT8(a1 + 28, a2 + 7);
                if ( !v4 )
                {
                  v4 = FwppDeepCopyToVerIndependent_UINT32(a1 + 32, a2 + 8);
                  if ( !v4 )
                  {
                    v4 = FwppDeepCopyToVerIndependent_UINT8(a1 + 36, a2 + 9);
                    if ( !v4 )
                    {
                      v4 = FwppDeepCopyToVerIndependent_UINT32(a1 + 40, a2 + 10);
                      if ( !v4 )
                      {
                        v4 = FwppDeepCopyToVerIndependent_UINT8(a1 + 44, a2 + 11);
                        if ( !v4 )
                        {
                          v4 = FwppDeepCopyToVerIndependent_UINT32(a1 + 48, a2 + 12);
                          if ( !v4 )
                          {
                            v4 = FwppDeepCopyToVerIndependent_UINT32(a1 + 52, a2 + 13);
                            if ( !v4 )
                            {
                              v4 = FwppDeepCopyToVerIndependent_UINT32(a1 + 56, a2 + 14);
                              if ( !v4 )
                              {
                                if ( a1 == -60 || (v5 = a2 + 15, a2 == (_DWORD *)-60LL) )
                                {
                                  v10 = WfpReportSysErrorAsNtStatus(
                                          v5,
                                          "FwppDeepCopyToVerIndependent_IPSEC_DOSP_FLAGS",
                                          3223453724LL);
                                  v4 = v10;
                                  if ( v10 )
                                  {
                                    WfpReportError(v10, "FwppDeepCopyToVerIndependent_IPSEC_DOSP_FLAGS");
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
                                  v4 = FwppArrayAllocAndDeepCopyToVerIndependent_UINT64(
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
                                  v4 = FwppArrayAllocAndDeepCopyToVerIndependent_UINT64(
                                         v7,
                                         *(unsigned int *)(a1 + 80),
                                         a2 + 22);
                                  if ( v4 )
                                    goto LABEL_30;
                                  a2[20] = *(_DWORD *)(a1 + 80);
                                }
                                v4 = FwppDeepCopyToVerIndependent_FWP_V6_ADDR_AND_MASK(a1 + 96, a2 + 24);
                                if ( !v4 )
                                {
                                  v8 = FwppDeepCopyToVerIndependent_FWP_V6_ADDR_AND_MASK(a1 + 113, (char *)a2 + 113);
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
    WfpReportError(v4, "FwppDeepCopyToVerIndependent_IPSEC_DOSP_OPTIONS0");
  return v4;
}

```

## disassembly

```asm
0x1800344d8  mov     [rsp+arg_0], rbx
0x1800344dd  mov     [rsp+arg_8], rsi
0x1800344e2  push    rdi
0x1800344e3  sub     rsp, 20h
0x1800344e7  mov     rsi, rdx
0x1800344ea  mov     rdi, rcx
0x1800344ed  test    rcx, rcx
0x1800344f0  jz      loc_18003475B
0x1800344f6  test    rdx, rdx
0x1800344f9  jz      loc_18003475B
0x1800344ff  call    FwppDeepCopyToVerIndependent_UINT32
0x180034504  mov     rbx, rax
0x180034507  test    rax, rax
0x18003450a  jnz     loc_1800346FC
0x180034510  lea     rdx, [rsi+4]
0x180034514  lea     rcx, [rdi+4]
0x180034518  call    FwppDeepCopyToVerIndependent_UINT32
0x18003451d  mov     rbx, rax
0x180034520  test    rax, rax
0x180034523  jnz     loc_1800346FC
0x180034529  lea     rdx, [rsi+8]
0x18003452d  lea     rcx, [rdi+8]
0x180034531  call    FwppDeepCopyToVerIndependent_UINT8
0x180034536  mov     rbx, rax
0x180034539  test    rax, rax
0x18003453c  jnz     loc_1800346FC
0x180034542  lea     rdx, [rsi+0Ch]
0x180034546  lea     rcx, [rdi+0Ch]
0x18003454a  call    FwppDeepCopyToVerIndependent_UINT32
0x18003454f  mov     rbx, rax
0x180034552  test    rax, rax
0x180034555  jnz     loc_1800346FC
0x18003455b  lea     rdx, [rsi+10h]
0x18003455f  lea     rcx, [rdi+10h]
0x180034563  call    FwppDeepCopyToVerIndependent_UINT32
0x180034568  mov     rbx, rax
0x18003456b  test    rax, rax
0x18003456e  jnz     loc_1800346FC
0x180034574  lea     rdx, [rsi+14h]
0x180034578  lea     rcx, [rdi+14h]
0x18003457c  call    FwppDeepCopyToVerIndependent_UINT8
0x180034581  mov     rbx, rax
0x180034584  test    rax, rax
0x180034587  jnz     loc_1800346FC
0x18003458d  lea     rdx, [rsi+18h]
0x180034591  lea     rcx, [rdi+18h]
0x180034595  call    FwppDeepCopyToVerIndependent_UINT32
0x18003459a  mov     rbx, rax
0x18003459d  test    rax, rax
0x1800345a0  jnz     loc_1800346FC
0x1800345a6  lea     rdx, [rsi+1Ch]
0x1800345aa  lea     rcx, [rdi+1Ch]
0x1800345ae  call    FwppDeepCopyToVerIndependent_UINT8
0x1800345b3  mov     rbx, rax
0x1800345b6  test    rax, rax
0x1800345b9  jnz     loc_1800346FC
0x1800345bf  lea     rdx, [rsi+20h]
0x1800345c3  lea     rcx, [rdi+20h]
0x1800345c7  call    FwppDeepCopyToVerIndependent_UINT32
0x1800345cc  mov     rbx, rax
0x1800345cf  test    rax, rax
0x1800345d2  jnz     loc_1800346FC
0x1800345d8  lea     rdx, [rsi+24h]
0x1800345dc  lea     rcx, [rdi+24h]
0x1800345e0  call    FwppDeepCopyToVerIndependent_UINT8
0x1800345e5  mov     rbx, rax
0x1800345e8  test    rax, rax
0x1800345eb  jnz     loc_1800346FC
0x1800345f1  lea     rdx, [rsi+28h]
0x1800345f5  lea     rcx, [rdi+28h]
0x1800345f9  call    FwppDeepCopyToVerIndependent_UINT32
0x1800345fe  mov     rbx, rax
0x180034601  test    rax, rax
0x180034604  jnz     loc_1800346FC
0x18003460a  lea     rdx, [rsi+2Ch]
0x18003460e  lea     rcx, [rdi+2Ch]
0x180034612  call    FwppDeepCopyToVerIndependent_UINT8
0x180034617  mov     rbx, rax
0x18003461a  test    rax, rax
0x18003461d  jnz     loc_1800346FC
0x180034623  lea     rdx, [rsi+30h]
0x180034627  lea     rcx, [rdi+30h]
0x18003462b  call    FwppDeepCopyToVerIndependent_UINT32
0x180034630  mov     rbx, rax
0x180034633  test    rax, rax
0x180034636  jnz     loc_1800346FC
0x18003463c  lea     rdx, [rsi+34h]
0x180034640  lea     rcx, [rdi+34h]
0x180034644  call    FwppDeepCopyToVerIndependent_UINT32
0x180034649  mov     rbx, rax
0x18003464c  test    rax, rax
0x18003464f  jnz     loc_1800346FC
0x180034655  lea     rdx, [rsi+38h]
0x180034659  lea     rcx, [rdi+38h]
0x18003465d  call    FwppDeepCopyToVerIndependent_UINT32
0x180034662  mov     rbx, rax
0x180034665  test    rax, rax
0x180034668  jnz     loc_1800346FC
0x18003466e  lea     rax, [rdi+3Ch]
0x180034672  test    rax, rax
0x180034675  jz      loc_18003472C
0x18003467b  lea     rcx, [rsi+3Ch]
0x18003467f  test    rcx, rcx
0x180034682  jz      loc_18003472C
0x180034688  mov     eax, [rax]
0x18003468a  mov     [rcx], eax
0x18003468c  mov     rcx, [rdi+48h]
0x180034690  test    rcx, rcx
0x180034693  jz      short loc_1800346AF
0x180034695  mov     edx, [rdi+40h]
0x180034698  lea     r8, [rsi+48h]
0x18003469c  call    FwppArrayAllocAndDeepCopyToVerIndependent_UINT64
0x1800346a1  mov     rbx, rax
0x1800346a4  test    rax, rax
0x1800346a7  jnz     short loc_1800346FC
0x1800346a9  mov     eax, [rdi+40h]
0x1800346ac  mov     [rsi+40h], eax
0x1800346af  mov     rcx, [rdi+58h]
0x1800346b3  test    rcx, rcx
0x1800346b6  jz      short loc_1800346D2
0x1800346b8  mov     edx, [rdi+50h]
0x1800346bb  lea     r8, [rsi+58h]
0x1800346bf  call    FwppArrayAllocAndDeepCopyToVerIndependent_UINT64
0x1800346c4  mov     rbx, rax
0x1800346c7  test    rax, rax
0x1800346ca  jnz     short loc_1800346FC
0x1800346cc  mov     eax, [rdi+50h]
0x1800346cf  mov     [rsi+50h], eax
0x1800346d2  lea     rdx, [rsi+60h]
0x1800346d6  lea     rcx, [rdi+60h]
0x1800346da  call    FwppDeepCopyToVerIndependent_FWP_V6_ADDR_AND_MASK
0x1800346df  mov     rbx, rax
0x1800346e2  test    rax, rax
0x1800346e5  jnz     short loc_1800346FC
0x1800346e7  lea     rdx, [rsi+71h]
0x1800346eb  lea     rcx, [rdi+71h]
0x1800346ef  call    FwppDeepCopyToVerIndependent_FWP_V6_ADDR_AND_MASK
0x1800346f4  mov     rbx, rax
0x1800346f7  test    rax, rax
0x1800346fa  jz      short loc_180034718
0x1800346fc  mov     rcx, rsi
0x1800346ff  call    FwppDeepFreeContentsOnly_IPSEC_DOSP_OPTIONS0
0x180034704  test    rbx, rbx
0x180034707  jz      short loc_180034718
0x180034709  lea     rdx, aFwppdeepcopyto_3; "FwppDeepCopyToVerIndependent_IPSEC_DOSP"...
0x180034710  mov     rcx, rbx
0x180034713  call    WfpReportError
0x180034718  mov     rsi, [rsp+28h+arg_8]
0x18003471d  mov     rax, rbx
0x180034720  mov     rbx, [rsp+28h+arg_0]
0x180034725  add     rsp, 20h
0x180034729  pop     rdi
0x18003472a  retn
0x18003472c  mov     r8d, 0C022001Ch
0x180034732  lea     rdx, aFwppdeepcopyto_22; "FwppDeepCopyToVerIndependent_IPSEC_DOSP"...
0x180034739  call    WfpReportSysErrorAsNtStatus
0x18003473e  mov     rbx, rax
0x180034741  test    rax, rax
0x180034744  jz      loc_18003468C
0x18003474a  lea     rdx, aFwppdeepcopyto_22; "FwppDeepCopyToVerIndependent_IPSEC_DOSP"...
0x180034751  mov     rcx, rax
0x180034754  call    WfpReportError
0x180034759  jmp     short loc_1800346FC
0x18003475b  mov     r8d, 0C022001Ch
0x180034761  lea     rdx, aFwppdeepcopyto_3; "FwppDeepCopyToVerIndependent_IPSEC_DOSP"...
0x180034768  call    WfpReportSysErrorAsNtStatus
0x18003476d  jmp     short loc_1800346F4
```
