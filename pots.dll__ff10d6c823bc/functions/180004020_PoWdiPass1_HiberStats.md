# PoWdiPass1_HiberStats

- ea: `0x180004020`
- end: `0x18000421d`
- name: `PoWdiPass1_HiberStats`
- size: `509`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800024e8`
- `0x180004020`

## string_xrefs

- `0x1800040b0`: `ResumeDecompressTime`
- `0x1800040cb`: `HiberWriteRate`
- `0x180004137`: `HiberCompressRate`

## pseudocode

```c
__int64 __fastcall PoWdiPass1_HiberStats(__int64 a1, _DWORD *a2)
{
  __int64 result; // rax
  int v5; // eax
  int v6; // [rsp+20h] [rbp-30h] BYREF
  int v7; // [rsp+24h] [rbp-2Ch] BYREF
  int v8; // [rsp+28h] [rbp-28h] BYREF
  int v9; // [rsp+2Ch] [rbp-24h] BYREF
  int v10; // [rsp+30h] [rbp-20h] BYREF
  int v11; // [rsp+34h] [rbp-1Ch] BYREF
  int v12; // [rsp+38h] [rbp-18h] BYREF
  int v13; // [rsp+3Ch] [rbp-14h] BYREF
  int v14; // [rsp+40h] [rbp-10h] BYREF
  _DWORD v15[3]; // [rsp+44h] [rbp-Ch] BYREF
  int v16; // [rsp+80h] [rbp+30h] BYREF
  int v17; // [rsp+88h] [rbp+38h] BYREF

  v9 = 0;
  v12 = 0;
  v7 = 0;
  v8 = 0;
  v10 = 0;
  v13 = 0;
  v15[0] = 0;
  v16 = 0;
  v17 = 0;
  v6 = 0;
  v11 = 0;
  v14 = 0;
  result = PoWdiGetULongProperty(a1, L"POSTTime", &v16);
  if ( (_DWORD)result )
  {
    result = PoWdiGetULongProperty(a1, L"ResumeAppTime", &v17);
    if ( (_DWORD)result )
    {
      result = PoWdiGetULongProperty(a1, L"ResumeIoTime", &v6);
      if ( (_DWORD)result )
      {
        result = PoWdiGetULongProperty(a1, L"ResumeDecompressTime", &v7);
        if ( (_DWORD)result )
        {
          result = PoWdiGetULongProperty(a1, L"HiberWriteRate", &v8);
          if ( (_DWORD)result )
          {
            result = PoWdiGetULongProperty(a1, L"BootPagesProcessed", &v9);
            if ( (_DWORD)result )
            {
              result = PoWdiGetULongProperty(a1, L"KernelPagesProcessed", &v10);
              if ( (_DWORD)result )
              {
                result = PoWdiGetULongProperty(a1, L"SecurePagesProcessed", &v11);
                if ( (_DWORD)result )
                {
                  result = PoWdiGetULongProperty(a1, L"HiberCompressRate", &v12);
                  if ( (_DWORD)result )
                  {
                    result = PoWdiGetULongProperty(a1, L"KernelResumeHiberFileTime", &v13);
                    if ( (_DWORD)result )
                    {
                      result = PoWdiGetULongProperty(a1, L"TotalHibernateTime", &v14);
                      if ( (_DWORD)result )
                      {
                        result = PoWdiGetULongProperty(a1, L"NoMultiStageResumeReason", v15);
                        if ( (_DWORD)result )
                        {
                          v5 = v16;
                          a2[34] |= 0x20u;
                          a2[1] |= 0x40000000u;
                          a2[37] = v5;
                          a2[38] = v17;
                          a2[45] = v6;
                          a2[46] = v7;
                          a2[44] = v8;
                          a2[39] = v9;
                          a2[40] = v10;
                          a2[41] = v11;
                          a2[42] = v12;
                          a2[43] = v13;
                          a2[47] = v14;
                          result = v15[0];
                          a2[48] = v15[0];
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
  return result;
}

```

## disassembly

```asm
0x180004020  mov     [rsp-18h+arg_0], rbx
0x180004025  push    rbp
0x180004026  push    rsi
0x180004027  push    rdi
0x180004028  mov     rbp, rsp
0x18000402b  sub     rsp, 50h
0x18000402f  xor     esi, esi
0x180004031  lea     r8, [rbp+arg_10]
0x180004035  mov     rdi, rdx
0x180004038  mov     [rbp+var_24], esi
0x18000403b  lea     rdx, aPosttime; "POSTTime"
0x180004042  mov     [rbp+var_18], esi
0x180004045  mov     [rbp+var_2C], esi
0x180004048  mov     rbx, rcx
0x18000404b  mov     [rbp+var_28], esi
0x18000404e  mov     [rbp+var_20], esi
0x180004051  mov     [rbp+var_14], esi
0x180004054  mov     [rbp+var_C], esi
0x180004057  mov     [rbp+arg_10], esi
0x18000405a  mov     [rbp+arg_18], esi
0x18000405d  mov     [rbp+var_30], esi
0x180004060  mov     [rbp+var_1C], esi
0x180004063  mov     [rbp+var_10], esi
0x180004066  call    PoWdiGetULongProperty
0x18000406b  test    eax, eax
0x18000406d  jz      loc_180004210
0x180004073  lea     r8, [rbp+arg_18]
0x180004077  mov     rcx, rbx
0x18000407a  lea     rdx, aResumeapptime; "ResumeAppTime"
0x180004081  call    PoWdiGetULongProperty
0x180004086  test    eax, eax
0x180004088  jz      loc_180004210
0x18000408e  lea     r8, [rbp+var_30]
0x180004092  mov     rcx, rbx
0x180004095  lea     rdx, aResumeiotime; "ResumeIoTime"
0x18000409c  call    PoWdiGetULongProperty
0x1800040a1  test    eax, eax
0x1800040a3  jz      loc_180004210
0x1800040a9  lea     r8, [rbp+var_2C]
0x1800040ad  mov     rcx, rbx
0x1800040b0  lea     rdx, aResumedecompre; "ResumeDecompressTime"
0x1800040b7  call    PoWdiGetULongProperty
0x1800040bc  test    eax, eax
0x1800040be  jz      loc_180004210
0x1800040c4  lea     r8, [rbp+var_28]
0x1800040c8  mov     rcx, rbx
0x1800040cb  lea     rdx, aHiberwriterate; "HiberWriteRate"
0x1800040d2  call    PoWdiGetULongProperty
0x1800040d7  test    eax, eax
0x1800040d9  jz      loc_180004210
0x1800040df  lea     r8, [rbp+var_24]
0x1800040e3  mov     rcx, rbx
0x1800040e6  lea     rdx, aBootpagesproce; "BootPagesProcessed"
0x1800040ed  call    PoWdiGetULongProperty
0x1800040f2  test    eax, eax
0x1800040f4  jz      loc_180004210
0x1800040fa  lea     r8, [rbp+var_20]
0x1800040fe  mov     rcx, rbx
0x180004101  lea     rdx, aKernelpagespro; "KernelPagesProcessed"
0x180004108  call    PoWdiGetULongProperty
0x18000410d  test    eax, eax
0x18000410f  jz      loc_180004210
0x180004115  lea     r8, [rbp+var_1C]
0x180004119  mov     rcx, rbx
0x18000411c  lea     rdx, aSecurepagespro; "SecurePagesProcessed"
0x180004123  call    PoWdiGetULongProperty
0x180004128  test    eax, eax
0x18000412a  jz      loc_180004210
0x180004130  lea     r8, [rbp+var_18]
0x180004134  mov     rcx, rbx
0x180004137  lea     rdx, aHibercompressr; "HiberCompressRate"
0x18000413e  call    PoWdiGetULongProperty
0x180004143  test    eax, eax
0x180004145  jz      loc_180004210
0x18000414b  lea     r8, [rbp+var_14]
0x18000414f  mov     rcx, rbx
0x180004152  lea     rdx, aKernelresumehi; "KernelResumeHiberFileTime"
0x180004159  call    PoWdiGetULongProperty
0x18000415e  test    eax, eax
0x180004160  jz      loc_180004210
0x180004166  lea     r8, [rbp+var_10]
0x18000416a  mov     rcx, rbx
0x18000416d  lea     rdx, aTotalhibernate; "TotalHibernateTime"
0x180004174  call    PoWdiGetULongProperty
0x180004179  test    eax, eax
0x18000417b  jz      loc_180004210
0x180004181  lea     r8, [rbp+var_C]
0x180004185  mov     rcx, rbx
0x180004188  lea     rdx, aNomultistagere; "NoMultiStageResumeReason"
0x18000418f  call    PoWdiGetULongProperty
0x180004194  test    eax, eax
0x180004196  jz      short loc_180004210
0x180004198  mov     eax, [rbp+arg_10]
0x18000419b  or      dword ptr [rdi+88h], 20h
0x1800041a2  bts     dword ptr [rdi+4], 1Eh
0x1800041a7  mov     [rdi+94h], eax
0x1800041ad  mov     eax, [rbp+arg_18]
0x1800041b0  mov     [rdi+98h], eax
0x1800041b6  mov     eax, [rbp+var_30]
0x1800041b9  mov     [rdi+0B4h], eax
0x1800041bf  mov     eax, [rbp+var_2C]
0x1800041c2  mov     [rdi+0B8h], eax
0x1800041c8  mov     eax, [rbp+var_28]
0x1800041cb  mov     [rdi+0B0h], eax
0x1800041d1  mov     eax, [rbp+var_24]
0x1800041d4  mov     [rdi+9Ch], eax
0x1800041da  mov     eax, [rbp+var_20]
0x1800041dd  mov     [rdi+0A0h], eax
0x1800041e3  mov     eax, [rbp+var_1C]
0x1800041e6  mov     [rdi+0A4h], eax
0x1800041ec  mov     eax, [rbp+var_18]
0x1800041ef  mov     [rdi+0A8h], eax
0x1800041f5  mov     eax, [rbp+var_14]
0x1800041f8  mov     [rdi+0ACh], eax
0x1800041fe  mov     eax, [rbp+var_10]
0x180004201  mov     [rdi+0BCh], eax
0x180004207  mov     eax, [rbp+var_C]
0x18000420a  mov     [rdi+0C0h], eax
0x180004210  mov     rbx, [rsp+50h+arg_0]
0x180004215  add     rsp, 50h
0x180004219  pop     rdi
0x18000421a  pop     rsi
0x18000421b  pop     rbp
0x18000421c  retn
```
