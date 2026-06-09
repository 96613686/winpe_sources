# GenerateFteMicForFTAssociationFrames(NWF_FT_CONTEXT *,uchar,uchar const *,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar *)

- ea: `0x1400497d8`
- end: `0x140049b66`
- name: `?GenerateFteMicForFTAssociationFrames@@YAJPEAUNWF_FT_CONTEXT@@EPEBE1K1K1KPEAE@Z`
- size: `910`
- prototype: `__int64 __fastcall(struct NWF_FT_CONTEXT *, char, const unsigned __int8 *, const unsigned __int8 *, size_t Size, unsigned __int8 *, size_t, unsigned __int8 *, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140042a1c`
- `0x140047e48`

## callees

- `0x14000d21c`
- `0x140020dc0`
- `0x140020f20`
- `0x14002525c`
- `0x14002f44c`
- `0x1400497d8`
- `0x14009bbb0`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400498ae`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400498ae`
- `ntoskrnl!ExAllocatePool2` at `0x1400498c3`
- `ntoskrnl!ExAllocatePool2` at `0x1400498c3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140049a1e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140049ae3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140049a1e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140049ae3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049a32`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049af7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049a32`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049af7`

## pseudocode

```c
__int64 __fastcall GenerateFteMicForFTAssociationFrames(
        struct NWF_FT_CONTEXT *a1,
        char a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        size_t Size,
        unsigned __int8 *a6,
        size_t a7,
        unsigned __int8 *a8,
        unsigned int a9,
        unsigned __int8 *a10)
{
  unsigned int MDDIELength; // ecx
  unsigned int v12; // esi
  unsigned int v13; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  char *Pool2; // rax
  char *v16; // rdi
  const unsigned __int8 *v17; // rcx
  char *v18; // r15
  __int16 v19; // ax
  const unsigned __int8 *v20; // rcx
  unsigned int v21; // ebx
  unsigned int v22; // ebx
  unsigned int v23; // ebx
  int v24; // eax
  unsigned int v25; // r12d
  _DEVICE_OBJECT *AttachedDevice; // rcx
  _DEVICE_OBJECT *v28; // rcx
  __int64 v30; // [rsp+40h] [rbp-49h] BYREF
  __int128 *v31; // [rsp+48h] [rbp-41h]
  const unsigned __int8 *v32; // [rsp+50h] [rbp-39h]
  const unsigned __int8 *v33; // [rsp+58h] [rbp-31h]
  void *Src; // [rsp+60h] [rbp-29h]
  void *v35; // [rsp+68h] [rbp-21h]
  __int128 v36; // [rsp+70h] [rbp-19h] BYREF

  MDDIELength = a1->MDDIELength;
  v32 = a3;
  v12 = a1->FTEIELength + MDDIELength + a1->RSNIELength + 13;
  v33 = a4;
  Src = a6;
  v35 = a8;
  v30 = (__int64)a10;
  if ( (_DWORD)Size && a6 )
    v12 += Size;
  if ( (_DWORD)a7 && a8 )
    v12 += a7;
  v13 = v12 + 16;
  if ( v12 >= 0xFFFFFFF0 )
    goto LABEL_41;
  if ( v13 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_16:
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_18;
  }
  if ( v13 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_16;
  }
  if ( v13 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_16;
  }
  if ( v13 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_16;
  }
  p_DeviceQueue = 0;
  Pool2 = (char *)ExAllocatePool2(64, v13, 2053731191);
LABEL_18:
  v16 = Pool2;
  if ( Pool2 )
  {
    v17 = v32;
    *((_DWORD *)Pool2 + 2) = 2053731191;
    v18 = Pool2 + 16;
    *(_QWORD *)Pool2 = p_DeviceQueue;
    *(_OWORD *)a1->pFTE_MIC = 0;
    *((_DWORD *)Pool2 + 4) = *(_DWORD *)v17;
    v19 = *((_WORD *)v17 + 2);
    v20 = v33;
    *((_WORD *)v18 + 2) = v19;
    *(_DWORD *)(v18 + 6) = *(_DWORD *)v20;
    *((_WORD *)v18 + 5) = *((_WORD *)v20 + 2);
    v18[12] = a2;
    memmove(v18 + 13, a1->pRSNIE, a1->RSNIELength);
    v21 = a1->RSNIELength + 13;
    memmove(&v18[v21], a1->pMDDIE, a1->MDDIELength);
    v22 = a1->MDDIELength + v21;
    memmove(&v18[v22], a1->pFTEIE, a1->FTEIELength);
    v23 = a1->FTEIELength + v22;
    if ( (_DWORD)Size && Src )
    {
      memmove(&v18[v23], Src, (unsigned int)Size);
      v23 += Size;
    }
    if ( (_DWORD)a7 && v35 )
      memmove(&v18[v23], v35, (unsigned int)a7);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 455, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
    v36 = 0;
    v24 = WL_CMAC_128((_DWORD)v18, v12, v30, a9, (__int64)&v36);
    v25 = v24;
    if ( v24 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
        v30 = (unsigned __int16)v12;
        v31 = (__int128 *)v18;
        WPP_SF__HEX_(AttachedDevice, 457, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, &v30);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          v28 = WPP_GLOBAL_Control->AttachedDevice;
          v30 = 16;
          v31 = &v36;
          WPP_SF__HEX_(v28, 458, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, &v30);
        }
      }
      *(_OWORD *)a1->pFTE_MIC = v36;
      if ( *(_QWORD *)v16 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v16, v16);
      else
        ExFreePoolWithTag(v16, *((_DWORD *)v16 + 2));
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          456,
          WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
          (unsigned int)v24);
      if ( *(_QWORD *)v16 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v16, v16);
      else
        ExFreePoolWithTag(v16, *((_DWORD *)v16 + 2));
      return v25;
    }
  }
LABEL_41:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      454,
      WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
      v12,
      -1073741670);
  return 3221225626LL;
}

```

## disassembly

```asm
0x1400497d8  mov     [rsp-8+arg_8], rbx
0x1400497dd  mov     [rsp-8+arg_10], rsi
0x1400497e2  push    rbp
0x1400497e3  push    rdi
0x1400497e4  push    r12
0x1400497e6  push    r13
0x1400497e8  push    r15
0x1400497ea  lea     rbp, [rsp-7]
0x1400497ef  sub     rsp, 90h
0x1400497f6  mov     rax, cs:__security_cookie
0x1400497fd  xor     rax, rsp
0x140049800  mov     [rbp+27h+var_30], rax
0x140049804  mov     r12d, dword ptr [rbp+27h+Size]
0x140049808  mov     r13, rcx
0x14004980b  mov     ecx, [rcx+34h]
0x14004980e  mov     rax, [rbp+27h+arg_48]
0x140049812  mov     [rbp+27h+var_60], r8
0x140049816  add     ecx, [r13+38h]
0x14004981a  mov     esi, [r13+3Ch]
0x14004981e  mov     r8, [rbp+27h+arg_28]
0x140049822  add     esi, 0Dh
0x140049825  add     esi, ecx
0x140049827  mov     [rbp+27h+var_80], dl
0x14004982a  mov     rdx, [rbp+27h+arg_38]
0x14004982e  mov     [rbp+27h+var_58], r9
0x140049832  mov     [rbp+27h+Src], r8
0x140049836  mov     [rbp+27h+var_48], rdx
0x14004983a  mov     qword ptr [rbp+27h+var_70], rax
0x14004983e  test    r12d, r12d
0x140049841  jz      short loc_14004984B
0x140049843  test    r8, r8
0x140049846  jz      short loc_14004984B
0x140049848  add     esi, r12d
0x14004984b  cmp     dword ptr [rbp+27h+arg_30], 0
0x14004984f  jbe     short loc_140049859
0x140049851  test    rdx, rdx
0x140049854  jz      short loc_140049859
0x140049856  add     esi, dword ptr [rbp+27h+arg_30]
0x140049859  lea     eax, [rsi+10h]
0x14004985c  cmp     eax, 10h
0x14004985f  jb      loc_140049B07
0x140049865  mov     ecx, 40h ; '@'
0x14004986a  mov     r15d, 7A697377h
0x140049870  cmp     eax, ecx
0x140049872  ja      short loc_14004987D
0x140049874  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14004987b  jmp     short loc_1400498AB
0x14004987d  cmp     eax, 100h
0x140049882  ja      short loc_14004988D
0x140049884  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004988b  jmp     short loc_1400498AB
0x14004988d  cmp     eax, 400h
0x140049892  ja      short loc_14004989D
0x140049894  lea     rbx, Lookaside
0x14004989b  jmp     short loc_1400498AB
0x14004989d  cmp     eax, 800h
0x1400498a2  ja      short loc_1400498BC
0x1400498a4  lea     rbx, stru_1400B31C0
0x1400498ab  mov     rcx, rbx; Lookaside
0x1400498ae  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400498b5  nop     dword ptr [rax+rax+00h]
0x1400498ba  jmp     short loc_1400498CF
0x1400498bc  xor     ebx, ebx
0x1400498be  mov     edx, eax
0x1400498c0  mov     r8d, r15d
0x1400498c3  call    cs:__imp_ExAllocatePool2
0x1400498ca  nop     dword ptr [rax+rax+00h]
0x1400498cf  mov     rdi, rax
0x1400498d2  test    rax, rax
0x1400498d5  jz      loc_140049B07
0x1400498db  mov     rcx, [rbp+27h+var_60]
0x1400498df  xorps   xmm0, xmm0
0x1400498e2  mov     [rax+8], r15d
0x1400498e6  lea     r15, [rax+10h]
0x1400498ea  mov     [rax], rbx
0x1400498ed  mov     rax, [r13+98h]
0x1400498f4  movups  xmmword ptr [rax], xmm0
0x1400498f7  mov     eax, [rcx]
0x1400498f9  mov     [r15], eax
0x1400498fc  movzx   eax, word ptr [rcx+4]
0x140049900  mov     rcx, [rbp+27h+var_58]
0x140049904  mov     [r15+4], ax
0x140049909  mov     eax, [rcx]
0x14004990b  mov     [r15+6], eax
0x14004990f  movzx   eax, word ptr [rcx+4]
0x140049913  lea     rcx, [r15+0Dh]; void *
0x140049917  mov     [r15+0Ah], ax
0x14004991c  mov     al, [rbp+27h+var_80]
0x14004991f  mov     [r15+0Ch], al
0x140049923  mov     r8d, [r13+3Ch]; Size
0x140049927  mov     rdx, [r13+50h]; Src
0x14004992b  call    memmove
0x140049930  mov     ebx, [r13+3Ch]
0x140049934  mov     r8d, [r13+34h]; Size
0x140049938  add     ebx, 0Dh
0x14004993b  mov     rdx, [r13+40h]; Src
0x14004993f  mov     ecx, ebx
0x140049941  add     rcx, r15; void *
0x140049944  call    memmove
0x140049949  add     ebx, [r13+34h]
0x14004994d  mov     r8d, [r13+38h]; Size
0x140049951  mov     rdx, [r13+48h]; Src
0x140049955  mov     ecx, ebx
0x140049957  add     rcx, r15; void *
0x14004995a  call    memmove
0x14004995f  add     ebx, [r13+38h]
0x140049963  test    r12d, r12d
0x140049966  jz      short loc_140049981
0x140049968  mov     rdx, [rbp+27h+Src]; Src
0x14004996c  test    rdx, rdx
0x14004996f  jz      short loc_140049981
0x140049971  mov     ecx, ebx
0x140049973  mov     r8, r12; Size
0x140049976  add     rcx, r15; void *
0x140049979  call    memmove
0x14004997e  add     ebx, r12d
0x140049981  cmp     dword ptr [rbp+27h+arg_30], 0
0x140049985  jbe     short loc_14004999E
0x140049987  mov     rdx, [rbp+27h+var_48]; Src
0x14004998b  test    rdx, rdx
0x14004998e  jz      short loc_14004999E
0x140049990  mov     r8d, dword ptr [rbp+27h+arg_30]; Size
0x140049994  mov     ecx, ebx
0x140049996  add     rcx, r15; void *
0x140049999  call    memmove
0x14004999e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400499a5  lea     rbx, WPP_GLOBAL_Control
0x1400499ac  cmp     rcx, rbx
0x1400499af  jz      short loc_1400499C6
0x1400499b1  mov     rcx, [rcx+18h]
0x1400499b5  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x1400499bc  mov     edx, 1C7h
0x1400499c1  call    WPP_SF_
0x1400499c6  mov     r9d, [rbp+27h+arg_40]
0x1400499ca  lea     rax, [rbp+27h+var_40]
0x1400499ce  mov     r8, qword ptr [rbp+27h+var_70]
0x1400499d2  xorps   xmm0, xmm0
0x1400499d5  mov     edx, esi
0x1400499d7  mov     [rsp+0B0h+var_90], rax
0x1400499dc  mov     rcx, r15
0x1400499df  movups  [rbp+27h+var_40], xmm0
0x1400499e3  call    WL_CMAC_128
0x1400499e8  mov     r12d, eax
0x1400499eb  test    eax, eax
0x1400499ed  jns     short loc_140049A46
0x1400499ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400499f6  cmp     rcx, rbx
0x1400499f9  jz      short loc_140049A13
0x1400499fb  mov     rcx, [rcx+18h]
0x1400499ff  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x140049a06  mov     edx, 1C8h
0x140049a0b  mov     r9d, eax
0x140049a0e  call    WPP_SF_d
0x140049a13  mov     rcx, [rdi]; Lookaside
0x140049a16  test    rcx, rcx
0x140049a19  jz      short loc_140049A2C
0x140049a1b  mov     rdx, rdi; Entry
0x140049a1e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140049a25  nop     dword ptr [rax+rax+00h]
0x140049a2a  jmp     short loc_140049A3E
0x140049a2c  mov     edx, [rdi+8]; Tag
0x140049a2f  mov     rcx, rdi; P
0x140049a32  call    cs:__imp_ExFreePoolWithTag
0x140049a39  nop     dword ptr [rax+rax+00h]
0x140049a3e  mov     eax, r12d
0x140049a41  jmp     loc_140049B3D
0x140049a46  mov     rcx, cs:WPP_GLOBAL_Control
0x140049a4d  cmp     rcx, rbx
0x140049a50  jz      short loc_140049AC9
0x140049a52  mov     rcx, [rcx+18h]
0x140049a56  lea     r9, [rbp+27h+var_70]
0x140049a5a  xorps   xmm0, xmm0
0x140049a5d  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x140049a64  movups  [rbp+27h+var_70], xmm0
0x140049a68  mov     word ptr [rbp+27h+var_70], si
0x140049a6c  mov     edx, 1C9h
0x140049a71  mov     qword ptr [rbp+27h+var_70+8], r15
0x140049a75  movaps  xmm0, [rbp+27h+var_70]
0x140049a79  movdqa  [rbp+27h+var_70], xmm0
0x140049a7e  call    WPP_SF__HEX_
0x140049a83  mov     rcx, cs:WPP_GLOBAL_Control
0x140049a8a  cmp     rcx, rbx
0x140049a8d  jz      short loc_140049AC9
0x140049a8f  mov     rcx, [rcx+18h]
0x140049a93  lea     r9, [rbp+27h+var_70]
0x140049a97  xorps   xmm0, xmm0
0x140049a9a  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x140049aa1  movups  [rbp+27h+var_70], xmm0
0x140049aa5  mov     eax, 10h
0x140049aaa  mov     edx, 1CAh
0x140049aaf  mov     word ptr [rbp+27h+var_70], ax
0x140049ab3  lea     rax, [rbp+27h+var_40]
0x140049ab7  mov     qword ptr [rbp+27h+var_70+8], rax
0x140049abb  movaps  xmm0, [rbp+27h+var_70]
0x140049abf  movdqa  [rbp+27h+var_70], xmm0
0x140049ac4  call    WPP_SF__HEX_
0x140049ac9  mov     rax, [r13+98h]
0x140049ad0  movups  xmm0, [rbp+27h+var_40]
0x140049ad4  movdqu  xmmword ptr [rax], xmm0
0x140049ad8  mov     rcx, [rdi]; Lookaside
0x140049adb  test    rcx, rcx
0x140049ade  jz      short loc_140049AF1
0x140049ae0  mov     rdx, rdi; Entry
0x140049ae3  call    cs:__imp_ExFreeToNPagedLookasideList
0x140049aea  nop     dword ptr [rax+rax+00h]
0x140049aef  jmp     short loc_140049B03
0x140049af1  mov     edx, [rdi+8]; Tag
0x140049af4  mov     rcx, rdi; P
0x140049af7  call    cs:__imp_ExFreePoolWithTag
0x140049afe  nop     dword ptr [rax+rax+00h]
0x140049b03  xor     eax, eax
0x140049b05  jmp     short loc_140049B3D
0x140049b07  mov     rcx, cs:WPP_GLOBAL_Control
0x140049b0e  lea     rbx, WPP_GLOBAL_Control
0x140049b15  mov     edi, 0C000009Ah
0x140049b1a  cmp     rcx, rbx
0x140049b1d  jz      short loc_140049B3B
0x140049b1f  mov     rcx, [rcx+18h]
0x140049b23  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x140049b2a  mov     edx, 1C6h
0x140049b2f  mov     dword ptr [rsp+0B0h+var_90], edi
0x140049b33  mov     r9d, esi
0x140049b36  call    WPP_SF_Dd
0x140049b3b  mov     eax, edi
0x140049b3d  mov     rcx, [rbp+27h+var_30]
0x140049b41  xor     rcx, rsp; StackCookie
0x140049b44  call    __security_check_cookie
0x140049b49  lea     r11, [rsp+0B0h+var_20]
0x140049b51  mov     rbx, [r11+38h]
0x140049b55  mov     rsi, [r11+40h]
0x140049b59  mov     rsp, r11
0x140049b5c  pop     r15
0x140049b5e  pop     r13
0x140049b60  pop     r12
0x140049b62  pop     rdi
0x140049b63  pop     rbp
0x140049b64  retn
```
