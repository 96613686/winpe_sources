# ValidateWithoutPlugin

- ea: `0x18000ea40`
- end: `0x18000ecd0`
- name: `ValidateWithoutPlugin`
- size: `656`
- prototype: `__int64 __fastcall(__int64, void *, NPrintTicketUtil::CPrintTicketWrapper *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e608`

## callees

- `0x1800060fc`
- `0x180008a68`
- `0x180008acc`
- `0x180008e68`
- `0x180009da8`
- `0x18000c6e4`
- `0x18000ea40`
- `0x18001c93c`
- `0x18001ea4c`
- `0x1800225ac`
- `0x1800225b8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000eb5c`
- `KERNEL32!GetLastError` at `0x18000eb5c`
- `KERNEL32!GetProcessHeap` at `0x18000eb05`
- `KERNEL32!GetProcessHeap` at `0x18000ec10`
- `KERNEL32!GetProcessHeap` at `0x18000eb05`
- `KERNEL32!GetProcessHeap` at `0x18000ec10`
- `KERNEL32!HeapAlloc` at `0x18000eb17`
- `KERNEL32!HeapAlloc` at `0x18000eb17`
- `KERNEL32!HeapFree` at `0x18000ec1e`
- `KERNEL32!HeapFree` at `0x18000ec1e`
- `WINSPOOL!DocumentPropertiesW` at `0x18000eb52`
- `WINSPOOL!DocumentPropertiesW` at `0x18000eb52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ecaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ecaf`

## pseudocode

```c
__int64 __fastcall ValidateWithoutPlugin(__int64 a1, void *a2, NPrintTicketUtil::CPrintTicketWrapper *a3)
{
  void *v6; // rcx
  int Devmode; // ebx
  struct _devicemodeW *v8; // r9
  HANDLE ProcessHeap; // rax
  size_t v10; // r15
  char *v11; // rax
  char *v12; // rsi
  signed int LastError; // eax
  int v14; // r14d
  int v15; // edx
  char *v16; // rax
  _OWORD *v17; // rax
  HANDLE v18; // rax
  struct IXMLDOMElement **v19; // r8
  unsigned __int16 **v20; // r9
  PDEVMODEW pDevModeInput; // [rsp+20h] [rbp-40h]
  struct _devicemodeW *pDevModeInputa; // [rsp+20h] [rbp-40h]
  struct NPrintTicketUtil::CPrintTicketWrapper *v24; // [rsp+30h] [rbp-30h] BYREF
  void **v25; // [rsp+38h] [rbp-28h] BYREF
  __int128 v26; // [rsp+40h] [rbp-20h]
  __int64 v27; // [rsp+50h] [rbp-10h]
  __int16 v28; // [rsp+58h] [rbp-8h]
  int v29; // [rsp+5Ch] [rbp-4h]
  SIZE_T dwBytes; // [rsp+90h] [rbp+30h] BYREF
  void *Src; // [rsp+A8h] [rbp+48h] BYREF

  LODWORD(dwBytes) = 0;
  v25 = &NPrintTicketUtil::CPrintTicketWrapper::`vftable';
  Src = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v6 = *(void **)(a1 + 24);
  v24 = 0;
  v26 = 0;
  Devmode = publicdm::GetDevmode(v6, 1, (unsigned int *)&dwBytes, &Src);
  if ( Devmode >= 0 )
  {
    if ( (*(_BYTE *)(a1 + 44) & 1) != 0
      || (Devmode = publicdm::DevmodeSnapshotFromJT(
                      (publicdm *)a2,
                      *(struct NPrintTicketUtil::CPrintTicketWrapper **)(a1 + 80),
                      (const unsigned __int16 *)Src,
                      v8),
          Devmode >= 0) )
    {
      LODWORD(pDevModeInput) = *(_DWORD *)(a1 + 40);
      Devmode = publicdm::JobTicketToPublicDevmode(
                  *(publicdm **)(a1 + 24),
                  a2,
                  *(const WCHAR **)(a1 + 88),
                  *(const unsigned __int16 **)(a1 + 80),
                  pDevModeInput->dmDeviceName,
                  (DEVMODEW *)Src);
      if ( Devmode >= 0 )
      {
        ProcessHeap = GetProcessHeap();
        v10 = (unsigned int)dwBytes;
        v11 = (char *)HeapAlloc(ProcessHeap, 0, (unsigned int)dwBytes);
        v12 = v11;
        if ( v11 )
        {
          memcpy_0(v11, Src, (unsigned int)v10);
          if ( DocumentPropertiesW(0, *(HANDLE *)(a1 + 24), 0, (PDEVMODEW)Src, (PDEVMODEW)Src, 0xAu) >= 0 )
            goto LABEL_11;
          LastError = GetLastError();
          Devmode = LastError;
          if ( LastError > 0 )
            Devmode = (unsigned __int16)LastError | 0x80070000;
          if ( Devmode >= 0 )
          {
LABEL_11:
            v15 = *((_DWORD *)v12 + 18);
            v14 = 0;
            if ( (v15 & 0xE) != 0 )
            {
              *((_DWORD *)v12 + 18) = v15 & 0xFFFEFFFF;
              *((_DWORD *)v12 + 18) = v15 ^ (*((_DWORD *)Src + 18) ^ v15) & 0x10000;
              v16 = (char *)Src;
              *(_OWORD *)(v12 + 102) = *(_OWORD *)((char *)Src + 102);
              *(_OWORD *)(v12 + 118) = *(_OWORD *)(v16 + 118);
              *(_OWORD *)(v12 + 134) = *(_OWORD *)(v16 + 134);
              *(_OWORD *)(v12 + 150) = *(_OWORD *)(v16 + 150);
            }
            v17 = Src;
            *(_OWORD *)v12 = *(_OWORD *)Src;
            *((_OWORD *)v12 + 1) = v17[1];
            *((_OWORD *)v12 + 2) = v17[2];
            *((_OWORD *)v12 + 3) = v17[3];
            if ( memcmp_0(Src, v12, v10) )
              v14 = 1;
          }
          else
          {
            v14 = 0;
          }
          v18 = GetProcessHeap();
          HeapFree(v18, 0, v12);
          if ( Devmode >= 0 )
          {
            Devmode = NPrintTicketUtil::CPrintTicketWrapper::StartDocument(a3, L"psf:PrintTicket", v19);
            if ( Devmode >= 0 )
            {
              if ( (*(_BYTE *)(a1 + 44) & 1) != 0
                || (Devmode = publicdm::DevmodeSnapshotToJT(
                                (publicdm *)Src,
                                *(struct _devicemodeW **)(a1 + 80),
                                (unsigned __int16 *)a3,
                                v20),
                    Devmode >= 0) )
              {
                LODWORD(pDevModeInputa) = *(_DWORD *)(a1 + 40);
                Devmode = publicdm::PublicDevmodeToJobTicket(
                            *(publicdm **)(a1 + 24),
                            *(void **)(a1 + 88),
                            *(const unsigned __int16 **)(a1 + 80),
                            (const unsigned __int16 *)Src,
                            pDevModeInputa,
                            (unsigned int)a3,
                            v24);
                if ( Devmode >= 0 )
                  Devmode = (v14 != 0) + 262145;
              }
            }
          }
        }
        else
        {
          Devmode = -2147024882;
        }
      }
    }
  }
  NCoreLibrary::TGenericSP<NPrintTicketUtil::TFeatureListRoot,NPrintTicketUtil::TAutoPtrFeatureList,NPrintTicketUtil::TFeatureListRoot *,0,NPrintTicketUtil::TFeatureListRoot const *>::Reset(&v24);
  NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v25);
  if ( Src )
    CoTaskMemFree(Src);
  return (unsigned int)Devmode;
}

```

## disassembly

```asm
0x18000ea40  mov     [rsp-28h+arg_8], rbx
0x18000ea45  mov     [rsp-28h+arg_10], rsi
0x18000ea4a  push    rbp
0x18000ea4b  push    rdi
0x18000ea4c  push    r12
0x18000ea4e  push    r14
0x18000ea50  push    r15
0x18000ea52  mov     rbp, rsp
0x18000ea55  sub     rsp, 60h
0x18000ea59  lea     rax, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x18000ea60  mov     dword ptr [rbp+dwBytes], 0
0x18000ea67  mov     [rbp+var_28], rax
0x18000ea6b  lea     r9, [rbp+Src]
0x18000ea6f  xor     eax, eax
0x18000ea71  mov     [rbp+Src], 0
0x18000ea79  mov     r12, r8
0x18000ea7c  mov     [rbp+var_10], 0
0x18000ea84  mov     rsi, rdx
0x18000ea87  mov     [rbp+var_8], ax
0x18000ea8b  mov     rdi, rcx
0x18000ea8e  mov     [rbp+var_4], eax
0x18000ea91  mov     rcx, [rcx+18h]
0x18000ea95  lea     edx, [rax+1]
0x18000ea98  xorps   xmm0, xmm0
0x18000ea9b  mov     [rbp+var_30], rax
0x18000ea9f  lea     r8, [rbp+dwBytes]
0x18000eaa3  movdqu  [rbp+var_20], xmm0
0x18000eaa8  call    ?GetDevmode@publicdm@@YAJPEAXW4DEVMODE_TYPE@1@PEAKPEAPEAU_devicemodeW@@@Z; publicdm::GetDevmode(void *,publicdm::DEVMODE_TYPE,ulong *,_devicemodeW * *)
0x18000eaad  mov     ebx, eax
0x18000eaaf  test    eax, eax
0x18000eab1  js      loc_18000EC94
0x18000eab7  test    byte ptr [rdi+2Ch], 1
0x18000eabb  jnz     short loc_18000EAD7
0x18000eabd  mov     r8, [rbp+Src]; unsigned __int16 *
0x18000eac1  mov     rcx, rsi; this
0x18000eac4  mov     rdx, [rdi+50h]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18000eac8  call    ?DevmodeSnapshotFromJT@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEBGPEAU_devicemodeW@@@Z; publicdm::DevmodeSnapshotFromJT(NPrintTicketUtil::CPrintTicketWrapper *,ushort const *,_devicemodeW *)
0x18000eacd  mov     ebx, eax
0x18000eacf  test    eax, eax
0x18000ead1  js      loc_18000EC94
0x18000ead7  mov     ecx, [rdi+28h]
0x18000eada  mov     rdx, rsi; void *
0x18000eadd  mov     rax, [rbp+Src]
0x18000eae1  mov     r9, [rdi+50h]; unsigned __int16 *
0x18000eae5  mov     r8, [rdi+58h]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18000eae9  mov     qword ptr [rsp+60h+fMode], rax; unsigned int
0x18000eaee  mov     dword ptr [rsp+60h+pDevModeInput], ecx; unsigned __int16 *
0x18000eaf2  mov     rcx, [rdi+18h]; this
0x18000eaf6  call    ?JobTicketToPublicDevmode@publicdm@@YAJPEAXPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEBG2KPEAU_devicemodeW@@@Z; publicdm::JobTicketToPublicDevmode(void *,NPrintTicketUtil::CPrintTicketWrapper *,ushort const *,ushort const *,ulong,_devicemodeW *)
0x18000eafb  mov     ebx, eax
0x18000eafd  test    eax, eax
0x18000eaff  js      loc_18000EC94
0x18000eb05  call    cs:__imp_GetProcessHeap
0x18000eb0b  mov     r15d, dword ptr [rbp+dwBytes]
0x18000eb0f  xor     edx, edx; dwFlags
0x18000eb11  mov     r8d, r15d; dwBytes
0x18000eb14  mov     rcx, rax; hHeap
0x18000eb17  call    cs:__imp_HeapAlloc
0x18000eb1d  mov     rsi, rax
0x18000eb20  test    rax, rax
0x18000eb23  jz      loc_18000EC8F
0x18000eb29  mov     rdx, [rbp+Src]; Src
0x18000eb2d  mov     r8d, r15d; Size
0x18000eb30  mov     rcx, rax; void *
0x18000eb33  call    memcpy_0
0x18000eb38  mov     r9, [rbp+Src]; pDevModeOutput
0x18000eb3c  xor     r8d, r8d; pDeviceName
0x18000eb3f  mov     rdx, [rdi+18h]; hPrinter
0x18000eb43  xor     ecx, ecx; hWnd
0x18000eb45  mov     [rsp+60h+fMode], 0Ah; fMode
0x18000eb4d  mov     [rsp+60h+pDevModeInput], r9; pDevModeInput
0x18000eb52  call    cs:__imp_DocumentPropertiesW
0x18000eb58  test    eax, eax
0x18000eb5a  jns     short loc_18000EB7D
0x18000eb5c  call    cs:__imp_GetLastError
0x18000eb62  mov     ebx, eax
0x18000eb64  test    eax, eax
0x18000eb66  jle     short loc_18000EB71
0x18000eb68  movzx   ebx, ax
0x18000eb6b  or      ebx, 80070000h
0x18000eb71  test    ebx, ebx
0x18000eb73  jns     short loc_18000EB7D
0x18000eb75  xor     r14d, r14d
0x18000eb78  jmp     loc_18000EC10
0x18000eb7d  mov     edx, [rsi+48h]
0x18000eb80  xor     r14d, r14d
0x18000eb83  test    dl, 0Eh
0x18000eb86  jz      short loc_18000EBD5
0x18000eb88  mov     eax, edx
0x18000eb8a  mov     ecx, edx
0x18000eb8c  btr     eax, 10h
0x18000eb90  mov     [rsi+48h], eax
0x18000eb93  mov     rax, [rbp+Src]
0x18000eb97  xor     ecx, [rax+48h]
0x18000eb9a  and     ecx, 10000h
0x18000eba0  xor     ecx, edx
0x18000eba2  mov     [rsi+48h], ecx
0x18000eba5  mov     rax, [rbp+Src]
0x18000eba9  movups  xmm0, xmmword ptr [rax+66h]
0x18000ebad  movups  xmmword ptr [rsi+66h], xmm0
0x18000ebb1  movups  xmm1, xmmword ptr [rax+76h]
0x18000ebb5  movups  xmmword ptr [rsi+76h], xmm1
0x18000ebb9  movups  xmm0, xmmword ptr [rax+86h]
0x18000ebc0  movups  xmmword ptr [rsi+86h], xmm0
0x18000ebc7  movups  xmm1, xmmword ptr [rax+96h]
0x18000ebce  movups  xmmword ptr [rsi+96h], xmm1
0x18000ebd5  mov     rax, [rbp+Src]
0x18000ebd9  mov     r8, r15; Size
0x18000ebdc  mov     rdx, rsi; Buf2
0x18000ebdf  movups  xmm0, xmmword ptr [rax]
0x18000ebe2  movups  xmmword ptr [rsi], xmm0
0x18000ebe5  movups  xmm1, xmmword ptr [rax+10h]
0x18000ebe9  movups  xmmword ptr [rsi+10h], xmm1
0x18000ebed  movups  xmm0, xmmword ptr [rax+20h]
0x18000ebf1  movups  xmmword ptr [rsi+20h], xmm0
0x18000ebf5  movups  xmm1, xmmword ptr [rax+30h]
0x18000ebf9  movups  xmmword ptr [rsi+30h], xmm1
0x18000ebfd  mov     rcx, [rbp+Src]; Buf1
0x18000ec01  call    memcmp_0
0x18000ec06  test    eax, eax
0x18000ec08  jz      short loc_18000EC10
0x18000ec0a  mov     r14d, 1
0x18000ec10  call    cs:__imp_GetProcessHeap
0x18000ec16  mov     r8, rsi; lpMem
0x18000ec19  xor     edx, edx; dwFlags
0x18000ec1b  mov     rcx, rax; hHeap
0x18000ec1e  call    cs:__imp_HeapFree
0x18000ec24  test    ebx, ebx
0x18000ec26  js      short loc_18000EC94
0x18000ec28  lea     rdx, aPsfPrintticket; "psf:PrintTicket"
0x18000ec2f  mov     rcx, r12; this
0x18000ec32  call    ?StartDocument@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEBGPEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::StartDocument(ushort const *,IXMLDOMElement * *)
0x18000ec37  mov     ebx, eax
0x18000ec39  test    eax, eax
0x18000ec3b  js      short loc_18000EC94
0x18000ec3d  test    byte ptr [rdi+2Ch], 1
0x18000ec41  jnz     short loc_18000EC59
0x18000ec43  mov     rdx, [rdi+50h]; struct _devicemodeW *
0x18000ec47  mov     r8, r12; unsigned __int16 *
0x18000ec4a  mov     rcx, [rbp+Src]; this
0x18000ec4e  call    ?DevmodeSnapshotToJT@publicdm@@YAJPEAU_devicemodeW@@PEBGPEAVCPrintTicketWrapper@NPrintTicketUtil@@@Z; publicdm::DevmodeSnapshotToJT(_devicemodeW *,ushort const *,NPrintTicketUtil::CPrintTicketWrapper *)
0x18000ec53  mov     ebx, eax
0x18000ec55  test    eax, eax
0x18000ec57  js      short loc_18000EC94
0x18000ec59  mov     eax, [rdi+28h]
0x18000ec5c  mov     r9, [rbp+Src]; unsigned __int16 *
0x18000ec60  mov     r8, [rdi+50h]; unsigned __int16 *
0x18000ec64  mov     rdx, [rdi+58h]; void *
0x18000ec68  mov     rcx, [rdi+18h]; this
0x18000ec6c  mov     qword ptr [rsp+60h+fMode], r12; unsigned int
0x18000ec71  mov     dword ptr [rsp+60h+pDevModeInput], eax; struct _devicemodeW *
0x18000ec75  call    ?PublicDevmodeToJobTicket@publicdm@@YAJPEAXPEBG1PEAU_devicemodeW@@KPEAVCPrintTicketWrapper@NPrintTicketUtil@@@Z; publicdm::PublicDevmodeToJobTicket(void *,ushort const *,ushort const *,_devicemodeW *,ulong,NPrintTicketUtil::CPrintTicketWrapper *)
0x18000ec7a  mov     ebx, eax
0x18000ec7c  test    eax, eax
0x18000ec7e  js      short loc_18000EC94
0x18000ec80  neg     r14d
0x18000ec83  sbb     ebx, ebx
0x18000ec85  neg     ebx
0x18000ec87  add     ebx, 40001h
0x18000ec8d  jmp     short loc_18000EC94
0x18000ec8f  mov     ebx, 8007000Eh
0x18000ec94  lea     rcx, [rbp+var_30]
0x18000ec98  call    ?Reset@?$TGenericSP@UTFeatureListRoot@NPrintTicketUtil@@VTAutoPtrFeatureList@2@PEAU12@$0A@PEBU12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::TFeatureListRoot,NPrintTicketUtil::TAutoPtrFeatureList,NPrintTicketUtil::TFeatureListRoot *,0,NPrintTicketUtil::TFeatureListRoot const *>::Reset(void)
0x18000ec9d  lea     rcx, [rbp+var_28]; this
0x18000eca1  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x18000eca6  mov     rcx, [rbp+Src]; pv
0x18000ecaa  test    rcx, rcx
0x18000ecad  jz      short loc_18000ECB5
0x18000ecaf  call    cs:__imp_CoTaskMemFree
0x18000ecb5  lea     r11, [rsp+60h+var_s0]
0x18000ecba  mov     eax, ebx
0x18000ecbc  mov     rbx, [r11+38h]
0x18000ecc0  mov     rsi, [r11+40h]
0x18000ecc4  mov     rsp, r11
0x18000ecc7  pop     r15
0x18000ecc9  pop     r14
0x18000eccb  pop     r12
0x18000eccd  pop     rdi
0x18000ecce  pop     rbp
0x18000eccf  retn
```
