# DwmQueryThumbnailSourceSize

- ea: `0x180008cc0`
- end: `0x180008e1c`
- name: `DwmQueryThumbnailSourceSize`
- size: `348`
- prototype: `HRESULT __stdcall(HTHUMBNAIL hThumbnail, PSIZE pSize)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000352c`
- `0x180004594`
- `0x180005b5c`
- `0x180008cc0`
- `0x18000af44`
- `0x18000bab0`
- `0x18000d0a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008d10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008d10`

## pseudocode

```c
HRESULT __stdcall DwmQueryThumbnailSourceSize(HTHUMBNAIL hThumbnail, PSIZE pSize)
{
  __int64 v2; // r8
  int v4; // ebx
  CApiPortClient *v5; // rcx
  int v6; // ebx
  void *v8; // [rsp+28h] [rbp-58h]
  void *v9; // [rsp+28h] [rbp-58h]
  int v10; // [rsp+40h] [rbp-40h] BYREF
  void **v11; // [rsp+48h] [rbp-38h] BYREF
  __int128 v12; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v13; // [rsp+60h] [rbp-20h] BYREF
  __int128 v14; // [rsp+64h] [rbp-1Ch]

  v4 = (int)hThumbnail;
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      Microsoft_Windows_Dwm_Api_Provider_Context,
      (__int64)ApipQueryThumbnailSourceSize_Start,
      v2,
      1,
      (__int64)&v13);
  if ( pSize )
  {
    v13 = 1073741859;
    v14 = 0;
    LODWORD(v14) = v4;
    v10 = 0;
    DWORD1(v14) = GetCurrentProcessId();
    v11 = &CStandardData::`vftable';
    v12 = 0;
    v6 = CApiPortClient::SendRequest(v5, &v13, 20, (const struct CAlpcView **)&v11, &v10, &v13, 20);
    std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>((char *)&v12 + 8);
    if ( v6 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_1800194F0, 2u, v6, 0x1F9u, v9);
    }
    else
    {
      v6 = v10;
      if ( v10 >= 0 )
        *pSize = *(struct tagSIZE *)((char *)&v14 + 8);
    }
  }
  else
  {
    v6 = -2147024809;
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_1800194F0, 2u, -2147024809, 0x1F0u, v8);
  }
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(Microsoft_Windows_Dwm_Api_Provider_Context, ApipQueryThumbnailSourceSize_Stop);
  return v6;
}

```

## disassembly

```asm
0x180008cc0  mov     [rsp-8+arg_10], rbx
0x180008cc5  mov     [rsp-8+arg_18], rdi
0x180008cca  push    rbp
0x180008ccb  mov     rbp, rsp
0x180008cce  sub     rsp, 80h
0x180008cd5  mov     rax, cs:__security_cookie
0x180008cdc  xor     rax, rsp
0x180008cdf  mov     [rbp+var_8], rax
0x180008ce3  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x180008cea  mov     rdi, rdx
0x180008ced  mov     rbx, rcx
0x180008cf0  jnz     loc_180008DDA
0x180008cf6  test    rdi, rdi
0x180008cf9  jz      loc_180008DA8
0x180008cff  xorps   xmm0, xmm0
0x180008d02  mov     [rbp+var_20], 40000023h
0x180008d09  movups  [rbp+var_1C], xmm0
0x180008d0d  mov     dword ptr [rbp+var_1C], ebx
0x180008d10  call    cs:__imp_GetCurrentProcessId
0x180008d16  xorps   xmm0, xmm0
0x180008d19  mov     [rbp+var_40], 0
0x180008d20  mov     dword ptr [rbp+var_1C+4], eax
0x180008d23  lea     r9, [rbp+var_38]; struct CStandardData *
0x180008d27  lea     rax, ??_7CStandardData@@6B@; const CStandardData::`vftable'
0x180008d2e  mov     [rbp+var_38], rax
0x180008d32  lea     rdx, [rbp+var_20]; void *
0x180008d36  mov     eax, 14h
0x180008d3b  mov     [rsp+80h+var_50], ax; __int16
0x180008d40  mov     r8d, eax; __int16
0x180008d43  lea     rax, [rbp+var_20]
0x180008d47  mov     [rsp+80h+var_58], rax; void *
0x180008d4c  lea     rax, [rbp+var_40]
0x180008d50  mov     [rsp+80h+var_60], rax; int *
0x180008d55  movdqu  [rbp+var_30], xmm0
0x180008d5a  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFAEBVCStandardData@@PEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,CStandardData const &,long *,void *,short)
0x180008d5f  lea     rcx, [rbp+var_30+8]
0x180008d63  mov     ebx, eax
0x180008d65  call    ??1?$unique_ptr@VCAlpcView@@U?$default_delete@VCAlpcView@@@std@@@std@@QEAA@XZ; std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>(void)
0x180008d6a  test    ebx, ebx
0x180008d6c  js      short loc_180008DD0
0x180008d6e  mov     ebx, [rbp+var_40]
0x180008d71  test    ebx, ebx
0x180008d73  js      short loc_180008D7C
0x180008d75  mov     rax, qword ptr [rbp+var_1C+8]
0x180008d79  mov     [rdi], rax
0x180008d7c  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x180008d83  jnz     short loc_180008E01
0x180008d85  mov     eax, ebx
0x180008d87  mov     rcx, [rbp+var_8]
0x180008d8b  xor     rcx, rsp; StackCookie
0x180008d8e  call    __security_check_cookie
0x180008d93  lea     r11, [rsp+80h+var_s0]
0x180008d9b  mov     rbx, [r11+20h]
0x180008d9f  mov     rdi, [r11+28h]
0x180008da3  mov     rsp, r11
0x180008da6  pop     rbp
0x180008da7  retn
0x180008da8  mov     ebx, 80070057h
0x180008dad  mov     dword ptr [rsp+80h+var_60], 1F0h; unsigned int
0x180008db5  mov     r8d, 2; unsigned int
0x180008dbb  lea     rdx, qword_1800194F0; int *
0x180008dc2  mov     r9d, ebx; int
0x180008dc5  lea     ecx, [r8+2]; unsigned int
0x180008dc9  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180008dce  jmp     short loc_180008D7C
0x180008dd0  mov     dword ptr [rsp+80h+var_60], 1F9h
0x180008dd8  jmp     short loc_180008DB5
0x180008dda  lea     rax, [rbp+var_20]
0x180008dde  mov     r9d, 1
0x180008de4  lea     rdx, ApipQueryThumbnailSourceSize_Start
0x180008deb  mov     [rsp+80h+var_60], rax
0x180008df0  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x180008df7  call    McGenEventWrite_EtwEventWriteTransfer
0x180008dfc  jmp     loc_180008CF6
0x180008e01  mov     r8d, ebx
0x180008e04  lea     rdx, ApipQueryThumbnailSourceSize_Stop
0x180008e0b  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x180008e12  call    McTemplateU0q_EtwEventWriteTransfer
0x180008e17  jmp     loc_180008D85
```
