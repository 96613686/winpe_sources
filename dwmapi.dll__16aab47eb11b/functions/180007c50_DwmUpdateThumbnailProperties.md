# DwmUpdateThumbnailProperties

- ea: `0x180007c50`
- end: `0x180007e0e`
- name: `DwmUpdateThumbnailProperties`
- size: `446`
- prototype: `HRESULT __stdcall(HTHUMBNAIL hThumbnailId, const DWM_THUMBNAIL_PROPERTIES *ptnProperties)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18000352c`
- `0x180004594`
- `0x180005b5c`
- `0x180007c50`
- `0x18000af44`
- `0x18000bab0`
- `0x18000d0a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007ce2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007ce2`

## pseudocode

```c
HRESULT __stdcall DwmUpdateThumbnailProperties(HTHUMBNAIL hThumbnailId, const DWM_THUMBNAIL_PROPERTIES *ptnProperties)
{
  __int64 v2; // r8
  DWORD CurrentProcessId; // eax
  __int128 v6; // xmm0
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  CApiPortClient *v9; // rcx
  int v10; // ebx
  void *v12; // [rsp+28h] [rbp-31h]
  void *v13; // [rsp+28h] [rbp-31h]
  int v14; // [rsp+40h] [rbp-19h] BYREF
  unsigned int v15[16]; // [rsp+48h] [rbp-11h] BYREF
  void **v16; // [rsp+88h] [rbp+2Fh] BYREF
  __int128 v17; // [rsp+90h] [rbp+37h] BYREF

  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      Microsoft_Windows_Dwm_Api_Provider_Context,
      (__int64)ApiUpdateThumbnailProperties_Start,
      v2,
      1,
      (__int64)&v16);
  if ( hThumbnailId
    && ptnProperties
    && ptnProperties->dwFlags
    && ((ptnProperties->dwFlags & 1) == 0
     || ptnProperties->rcDestination.right >= ptnProperties->rcDestination.left
     && ptnProperties->rcDestination.bottom >= ptnProperties->rcDestination.top)
    && ((ptnProperties->dwFlags & 2) == 0
     || ptnProperties->rcSource.right >= ptnProperties->rcSource.left
     && ptnProperties->rcSource.bottom >= ptnProperties->rcSource.top) )
  {
    memset(&v15[2], 0, 40);
    v15[0] = 1073741856;
    v15[1] = (unsigned int)hThumbnailId;
    CurrentProcessId = GetCurrentProcessId();
    v6 = *(_OWORD *)&ptnProperties->dwFlags;
    v15[2] = CurrentProcessId;
    v7 = *(_OWORD *)&ptnProperties->rcDestination.bottom;
    v16 = &CStandardData::`vftable';
    v14 = 0;
    *(_OWORD *)&v15[3] = v6;
    v8 = *(_OWORD *)((char *)&ptnProperties->rcSource.right + 1);
    *(_OWORD *)&v15[7] = v7;
    *(_OWORD *)((char *)&v15[10] + 1) = v8;
    v17 = 0;
    v10 = CApiPortClient::SendRequest(v9, v15, 57, (const struct CAlpcView **)&v16, &v14, 0, 0);
    std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>((char *)&v17 + 8);
    if ( v10 < 0 )
      MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_1800194A0, 2u, v10, 0x1B0u, v13);
    else
      v10 = v14;
  }
  else
  {
    v10 = -2147024809;
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_1800194A0, 2u, -2147024809, 0x1A5u, v12);
  }
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(Microsoft_Windows_Dwm_Api_Provider_Context, ApiUpdateThumbnailProperties_Stop);
  return v10;
}

```

## disassembly

```asm
0x180007c50  mov     [rsp-8+arg_10], rbx
0x180007c55  mov     [rsp-8+arg_18], rdi
0x180007c5a  push    rbp
0x180007c5b  lea     rbp, [rsp-57h]
0x180007c60  sub     rsp, 0B0h
0x180007c67  mov     rax, cs:__security_cookie
0x180007c6e  xor     rax, rsp
0x180007c71  mov     [rbp+57h+var_10], rax
0x180007c75  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x180007c7c  mov     rbx, rdx
0x180007c7f  mov     rdi, rcx
0x180007c82  jnz     loc_180007DCC
0x180007c88  test    rdi, rdi
0x180007c8b  jz      loc_180007D84
0x180007c91  test    rbx, rbx
0x180007c94  jz      loc_180007D84
0x180007c9a  cmp     dword ptr [rbx], 0
0x180007c9d  jz      loc_180007D84
0x180007ca3  test    byte ptr [rbx], 1
0x180007ca6  jz      short loc_180007CC0
0x180007ca8  mov     eax, [rbx+4]
0x180007cab  cmp     [rbx+0Ch], eax
0x180007cae  jl      loc_180007D84
0x180007cb4  mov     eax, [rbx+8]
0x180007cb7  cmp     [rbx+10h], eax
0x180007cba  jl      loc_180007D84
0x180007cc0  test    byte ptr [rbx], 2
0x180007cc3  jnz     loc_180007DAC
0x180007cc9  xorps   xmm0, xmm0
0x180007ccc  movups  [rbp+57h+var_68], xmm0
0x180007cd0  mov     dword ptr [rbp+57h+var_68], 40000020h
0x180007cd7  mov     dword ptr [rbp+57h+var_68+4], edi
0x180007cda  movups  [rbp+57h+var_58], xmm0
0x180007cde  movups  [rbp+57h+var_48], xmm0
0x180007ce2  call    cs:__imp_GetCurrentProcessId
0x180007ce8  movups  xmm0, xmmword ptr [rbx]
0x180007ceb  mov     dword ptr [rbp+57h+var_68+8], eax
0x180007cee  lea     rax, ??_7CStandardData@@6B@; const CStandardData::`vftable'
0x180007cf5  movups  xmm1, xmmword ptr [rbx+10h]
0x180007cf9  mov     [rbp+57h+var_28], rax
0x180007cfd  lea     r9, [rbp+57h+var_28]; struct CStandardData *
0x180007d01  xor     eax, eax
0x180007d03  mov     [rbp+57h+var_70], 0
0x180007d0a  mov     [rsp+0B0h+var_80], ax; __int16
0x180007d0f  lea     rdx, [rbp+57h+var_68]; void *
0x180007d13  movups  [rbp+57h+var_68+0Ch], xmm0
0x180007d17  mov     [rsp+0B0h+var_88], rax; void *
0x180007d1c  movups  xmm0, xmmword ptr [rbx+1Dh]
0x180007d20  lea     r8d, [rax+39h]; __int16
0x180007d24  movups  [rbp+57h+var_58+0Ch], xmm1
0x180007d28  lea     rax, [rbp+57h+var_70]
0x180007d2c  movups  [rbp+57h+var_48+9], xmm0
0x180007d30  mov     [rsp+0B0h+var_90], rax; int *
0x180007d35  xorps   xmm0, xmm0
0x180007d38  movdqu  [rbp+57h+var_20], xmm0
0x180007d3d  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFAEBVCStandardData@@PEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,CStandardData const &,long *,void *,short)
0x180007d42  lea     rcx, [rbp+57h+var_20+8]
0x180007d46  mov     ebx, eax
0x180007d48  call    ??1?$unique_ptr@VCAlpcView@@U?$default_delete@VCAlpcView@@@std@@@std@@QEAA@XZ; std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>(void)
0x180007d4d  test    ebx, ebx
0x180007d4f  js      short loc_180007DC2
0x180007d51  mov     ebx, [rbp+57h+var_70]
0x180007d54  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x180007d5b  jnz     loc_180007DF3
0x180007d61  mov     eax, ebx
0x180007d63  mov     rcx, [rbp+57h+var_10]
0x180007d67  xor     rcx, rsp; StackCookie
0x180007d6a  call    __security_check_cookie
0x180007d6f  lea     r11, [rsp+0B0h+var_s0]
0x180007d77  mov     rbx, [r11+20h]
0x180007d7b  mov     rdi, [r11+28h]
0x180007d7f  mov     rsp, r11
0x180007d82  pop     rbp
0x180007d83  retn
0x180007d84  mov     ebx, 80070057h
0x180007d89  mov     dword ptr [rsp+0B0h+var_90], 1A5h; unsigned int
0x180007d91  mov     r8d, 2; unsigned int
0x180007d97  lea     rdx, qword_1800194A0; int *
0x180007d9e  mov     r9d, ebx; int
0x180007da1  lea     ecx, [r8+2]; unsigned int
0x180007da5  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180007daa  jmp     short loc_180007D54
0x180007dac  mov     eax, [rbx+14h]
0x180007daf  cmp     [rbx+1Ch], eax
0x180007db2  jl      short loc_180007D84
0x180007db4  mov     eax, [rbx+18h]
0x180007db7  cmp     [rbx+20h], eax
0x180007dba  jge     loc_180007CC9
0x180007dc0  jmp     short loc_180007D84
0x180007dc2  mov     dword ptr [rsp+0B0h+var_90], 1B0h
0x180007dca  jmp     short loc_180007D91
0x180007dcc  lea     rax, [rbp+57h+var_28]
0x180007dd0  mov     r9d, 1
0x180007dd6  lea     rdx, ApiUpdateThumbnailProperties_Start
0x180007ddd  mov     [rsp+0B0h+var_90], rax
0x180007de2  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x180007de9  call    McGenEventWrite_EtwEventWriteTransfer
0x180007dee  jmp     loc_180007C88
0x180007df3  mov     r8d, ebx
0x180007df6  lea     rdx, ApiUpdateThumbnailProperties_Stop
0x180007dfd  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x180007e04  call    McTemplateU0q_EtwEventWriteTransfer
0x180007e09  jmp     loc_180007D61
```
