# tpm12class::TPMW8_PCR_Read::DecodeRsp(ushort *)

- ea: `0x180021050`
- end: `0x180021273`
- name: `?DecodeRsp@TPMW8_PCR_Read@tpm12class@@UEAAJPEAG@Z`
- size: `547`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_PCR_Read *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003270`
- `0x180003cf0`
- `0x18000a534`
- `0x18000a66c`
- `0x18001f650`
- `0x180021050`
- `0x1800241f0`
- `0x1800242bc`
- `0x1800249fc`
- `0x180059010`

## string_xrefs

- `0x1800210bb`: `--TPM2_PCR_Read: Parameters------------------------------------------\n`
- `0x1800210d8`: `pcrUpdateCounter`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_PCR_Read::DecodeRsp(tpm12class::TPMW8_PCR_Read *this, unsigned __int16 *a2)
{
  signed int v4; // ebx
  unsigned __int16 *v5; // r8
  __int64 v6; // rdx
  __int64 v7; // rax
  unsigned __int16 *v8; // rcx
  unsigned __int16 *v9; // rcx
  unsigned int v10; // esi
  __int64 v11; // rcx
  struct TPM_SYMBOLTABLE_ENTRY *v13; // [rsp+20h] [rbp-248h]
  unsigned __int16 v14; // [rsp+30h] [rbp-238h] BYREF
  _BYTE v15[510]; // [rsp+32h] [rbp-236h] BYREF

  v14 = 0;
  v4 = 0;
  memset_0(v15, 0, sizeof(v15));
  if ( TraceEnabled() )
  {
    v4 = tpm12class::TPMW8_COMMAND::DecodeRsp(this, a2);
    if ( v4 >= 0 )
    {
      v4 = TraceDirect(L"--TPM2_PCR_Read: Parameters------------------------------------------\r\n");
      if ( v4 >= 0 )
      {
        v4 = TraceUINT32Value(a2, L"pcrUpdateCounter", *((_DWORD *)this + 66), 1u, 0, 0);
        if ( v4 >= 0 )
        {
          v5 = &v14;
          v6 = 256;
          v7 = 2147483646;
          v8 = a2;
          do
          {
            if ( !v7 )
              break;
            if ( !*v8 )
              break;
            *v5++ = *v8++;
            --v7;
            --v6;
          }
          while ( v6 );
          v9 = v5 - 1;
          v4 = v6 == 0 ? 0x8007007A : 0;
          if ( v6 )
            v9 = v5;
          *v9 = 0;
          if ( v6 )
          {
            v4 = StringCchCatW(&v14, 0x100u, L"pcrSelectionOut.");
            if ( v4 >= 0 )
            {
              v4 = (*(__int64 (__fastcall **)(char *, unsigned __int16 *))(*((_QWORD *)this + 34) + 40LL))(
                     (char *)this + 272,
                     &v14);
              if ( v4 >= 0 )
              {
                v4 = StringCchPrintfW(&v14, 0x100u, L"%spcrValues.", a2);
                if ( v4 >= 0 )
                {
                  v4 = TraceUINT32Value(&v14, L"count", *((_DWORD *)this + 86), 1u, 0, 0);
                  if ( v4 >= 0 )
                  {
                    if ( *((_DWORD *)this + 86) )
                    {
                      v10 = 0;
                      do
                      {
                        LODWORD(v13) = v10;
                        v4 = StringCchPrintfW(&v14, 0x100u, L"%spcrValues.digests[%d].", a2, v13);
                        if ( v4 < 0 )
                          break;
                        v11 = *((_QWORD *)this + 44) + 72LL * v10;
                        v4 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v11 + 40LL))(v11, &v14);
                        if ( v4 < 0 )
                          break;
                        ++v10;
                      }
                      while ( v10 < *((_DWORD *)this + 86) );
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
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180021050  mov     [rsp+arg_10], rbx
0x180021055  push    rbp
0x180021056  push    rsi
0x180021057  push    rdi
0x180021058  push    r14
0x18002105a  push    r15
0x18002105c  sub     rsp, 240h
0x180021063  mov     rax, cs:__security_cookie
0x18002106a  xor     rax, rsp
0x18002106d  mov     [rsp+268h+var_38], rax
0x180021075  mov     rbp, rdx
0x180021078  mov     rdi, rcx
0x18002107b  xor     r14d, r14d
0x18002107e  lea     rcx, [rsp+268h+var_236]; void *
0x180021083  xor     edx, edx; Val
0x180021085  mov     [rsp+268h+var_238], r14w
0x18002108b  mov     r8d, 1FEh; Size
0x180021091  mov     ebx, r14d
0x180021094  call    memset_0
0x180021099  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x18002109e  test    al, al
0x1800210a0  jz      loc_180021249
0x1800210a6  mov     rdx, rbp; unsigned __int16 *
0x1800210a9  mov     rcx, rdi; this
0x1800210ac  call    ?DecodeRsp@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z; tpm12class::TPMW8_COMMAND::DecodeRsp(ushort *)
0x1800210b1  mov     ebx, eax
0x1800210b3  test    eax, eax
0x1800210b5  js      loc_180021249
0x1800210bb  lea     rcx, aTpm2PcrReadPar; "--TPM2_PCR_Read: Parameters------------"...
0x1800210c2  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x1800210c7  mov     ebx, eax
0x1800210c9  test    eax, eax
0x1800210cb  js      loc_180021249
0x1800210d1  mov     r8d, [rdi+108h]; unsigned int
0x1800210d8  lea     rdx, aPcrupdatecount; "pcrUpdateCounter"
0x1800210df  mov     [rsp+268h+var_240], r14b; unsigned __int8
0x1800210e4  mov     r9b, 1; unsigned __int8
0x1800210e7  mov     rcx, rbp; unsigned __int16 *
0x1800210ea  mov     [rsp+268h+var_248], r14; struct TPM_SYMBOLTABLE_ENTRY *
0x1800210ef  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800210f4  mov     ebx, eax
0x1800210f6  test    eax, eax
0x1800210f8  js      loc_180021249
0x1800210fe  mov     r15d, 100h
0x180021104  lea     r8, [rsp+268h+var_238]
0x180021109  mov     edx, r15d
0x18002110c  mov     eax, 7FFFFFFEh
0x180021111  mov     rcx, rbp
0x180021114  test    rax, rax
0x180021117  jz      short loc_180021138
0x180021119  movzx   r9d, word ptr [rcx]
0x18002111d  test    r9w, r9w
0x180021121  jz      short loc_180021138
0x180021123  mov     [r8], r9w
0x180021127  add     rcx, 2
0x18002112b  add     r8, 2
0x18002112f  dec     rax
0x180021132  sub     rdx, 1
0x180021136  jnz     short loc_180021114
0x180021138  mov     rax, rdx
0x18002113b  lea     rcx, [r8-2]
0x18002113f  neg     rax
0x180021142  sbb     ebx, ebx
0x180021144  not     ebx
0x180021146  and     ebx, 8007007Ah
0x18002114c  test    rdx, rdx
0x18002114f  cmovnz  rcx, r8
0x180021153  mov     [rcx], r14w
0x180021157  jz      loc_180021249
0x18002115d  lea     r8, aPcrselectionou; "pcrSelectionOut."
0x180021164  mov     rdx, r15; unsigned __int64
0x180021167  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x18002116c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180021171  mov     ebx, eax
0x180021173  test    eax, eax
0x180021175  js      loc_180021249
0x18002117b  lea     rcx, [rdi+110h]
0x180021182  mov     rax, [rcx]
0x180021185  lea     rdx, [rsp+268h+var_238]
0x18002118a  mov     rax, [rax+28h]
0x18002118e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021193  mov     ebx, eax
0x180021195  test    eax, eax
0x180021197  js      loc_180021249
0x18002119d  mov     r9, rbp
0x1800211a0  lea     r8, aSpcrvalues; "%spcrValues."
0x1800211a7  mov     rdx, r15; unsigned __int64
0x1800211aa  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x1800211af  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800211b4  mov     ebx, eax
0x1800211b6  test    eax, eax
0x1800211b8  js      loc_180021249
0x1800211be  mov     r8d, [rdi+158h]; unsigned int
0x1800211c5  lea     rdx, aCount; "count"
0x1800211cc  mov     [rsp+268h+var_240], r14b; unsigned __int8
0x1800211d1  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x1800211d6  mov     r9b, 1; unsigned __int8
0x1800211d9  mov     [rsp+268h+var_248], r14; struct TPM_SYMBOLTABLE_ENTRY *
0x1800211de  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800211e3  mov     ebx, eax
0x1800211e5  test    eax, eax
0x1800211e7  js      short loc_180021249
0x1800211e9  mov     eax, [rdi+158h]
0x1800211ef  test    eax, eax
0x1800211f1  jz      short loc_180021249
0x1800211f3  mov     esi, r14d
0x1800211f6  mov     r9, rbp
0x1800211f9  mov     dword ptr [rsp+268h+var_248], esi
0x1800211fd  lea     r8, aSpcrvaluesDige; "%spcrValues.digests[%d]."
0x180021204  mov     rdx, r15; unsigned __int64
0x180021207  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x18002120c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021211  mov     ebx, eax
0x180021213  test    eax, eax
0x180021215  js      short loc_180021249
0x180021217  mov     eax, esi
0x180021219  lea     rdx, [rsp+268h+var_238]
0x18002121e  lea     rcx, [rax+rax*8]
0x180021222  mov     rax, [rdi+160h]
0x180021229  lea     rcx, [rax+rcx*8]
0x18002122d  mov     rax, [rcx]
0x180021230  mov     rax, [rax+28h]
0x180021234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021239  mov     ebx, eax
0x18002123b  test    eax, eax
0x18002123d  js      short loc_180021249
0x18002123f  inc     esi
0x180021241  cmp     esi, [rdi+158h]
0x180021247  jb      short loc_1800211F6
0x180021249  mov     eax, ebx
0x18002124b  mov     rcx, [rsp+268h+var_38]
0x180021253  xor     rcx, rsp; StackCookie
0x180021256  call    __security_check_cookie
0x18002125b  mov     rbx, [rsp+268h+arg_10]
0x180021263  add     rsp, 240h
0x18002126a  pop     r15
0x18002126c  pop     r14
0x18002126e  pop     rdi
0x18002126f  pop     rsi
0x180021270  pop     rbp
0x180021271  retn
```
