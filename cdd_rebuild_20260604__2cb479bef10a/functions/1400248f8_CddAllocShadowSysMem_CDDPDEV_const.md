# CddAllocShadowSysMem(CDDPDEV * const)

- ea: `0x1400248f8`
- end: `0x140024cae`
- name: `?CddAllocShadowSysMem@@YAXQEAUCDDPDEV@@@Z`
- size: `950`
- prototype: `void __fastcall(struct CDDPDEV *const)`
- caller_count: `12`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140002504`
- `0x140004904`
- `0x140005cc0`
- `0x140006a70`
- `0x140007b00`
- `0x14000919c`
- `0x1400161b0`
- `0x140017518`
- `0x140019458`
- `0x140022e70`
- `0x1400235c0`
- `0x140023e60`

## callees

- `0x140018e30`
- `0x1400248f8`
- `0x14002c038`
- `0x1400371f0`
- `0x1400372d0`

## import_xrefs

- `ntoskrnl!MmProbeAndLockPages` at `0x140024b80`
- `ntoskrnl!MmProbeAndLockPages` at `0x140024b80`
- `ntoskrnl!MmSizeOfMdl` at `0x140024acd`
- `ntoskrnl!MmSizeOfMdl` at `0x140024acd`
- `ntoskrnl!MmMapViewInSessionSpace` at `0x1400249fd`
- `ntoskrnl!MmMapViewInSessionSpace` at `0x1400249fd`
- `ntoskrnl!MmCreateSection` at `0x14002497f`
- `ntoskrnl!MmCreateSection` at `0x14002497f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024bf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024bf7`
- `ntoskrnl!ExAllocatePool2` at `0x140024aea`
- `ntoskrnl!ExAllocatePool2` at `0x140024aea`
- `watchdog!WdLogSingleEntry2` at `0x140024b0e`
- `watchdog!WdLogSingleEntry2` at `0x140024ba5`
- `watchdog!WdLogSingleEntry2` at `0x140024b0e`
- `watchdog!WdLogSingleEntry2` at `0x140024ba5`
- `watchdog!WdLogSingleEntry3` at `0x14002499b`
- `watchdog!WdLogSingleEntry3` at `0x140024a22`
- `watchdog!WdLogSingleEntry3` at `0x14002499b`
- `watchdog!WdLogSingleEntry3` at `0x140024a22`
- `watchdog!WdLogSingleEntry1` at `0x140024c33`
- `watchdog!WdLogSingleEntry1` at `0x140024c33`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400249b2`
- `watchdog!WdLogNewEntry5_WdError` at `0x140024a3b`
- `watchdog!WdLogNewEntry5_WdError` at `0x140024bbb`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400249b2`
- `watchdog!WdLogNewEntry5_WdError` at `0x140024a3b`
- `watchdog!WdLogNewEntry5_WdError` at `0x140024bbb`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140024c4a`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140024c4a`

## pseudocode

```c
void __fastcall CddAllocShadowSysMem(struct CDDPDEV *const a1)
{
  PVOID *v2; // r14
  SIZE_T *v3; // rsi
  int v4; // eax
  int v5; // esi
  _QWORD *v6; // rax
  PVOID *v7; // r12
  NTSTATUS v8; // eax
  _QWORD *v9; // rax
  SIZE_T v10; // r14
  __int64 Pool2; // rax
  SIZE_T v12; // r9
  unsigned __int64 v13; // rdx
  _QWORD *v14; // rax
  _DWORD v15[2]; // [rsp+40h] [rbp-A8h] BYREF
  ULONG_PTR ViewSize[3]; // [rsp+48h] [rbp-A0h] BYREF
  _DWORD v17[2]; // [rsp+60h] [rbp-88h] BYREF
  __int64 v18; // [rsp+68h] [rbp-80h]
  __int128 v19; // [rsp+70h] [rbp-78h]
  __int64 v20; // [rsp+80h] [rbp-68h]
  __int64 v21; // [rsp+88h] [rbp-60h]
  int v22; // [rsp+90h] [rbp-58h]
  int v23; // [rsp+94h] [rbp-54h]
  __int64 v24; // [rsp+98h] [rbp-50h]

  ViewSize[1] = (ULONG_PTR)a1;
  if ( *((_QWORD *)a1 + 317) )
    return;
  v2 = (PVOID *)((char *)a1 + 2544);
  v3 = (SIZE_T *)((char *)a1 + 2560);
  if ( !*((_QWORD *)a1 + 318) )
  {
    v15[1] = 0;
    v15[0] = *(_DWORD *)v3;
    v4 = ((__int64 (__fastcall *)(char *, __int64, _QWORD, _DWORD *, int, int, _QWORD, _QWORD))MmCreateSection)(
           (char *)a1 + 2544,
           6,
           0,
           v15,
           4,
           0x8000000,
           0,
           0);
    if ( v4 < 0 )
    {
      WdLogSingleEntry3(2, a1, *v3, v4);
      v5 = 1695;
LABEL_5:
      WdLogGlobalForLineNumber = v5;
      v6 = (_QWORD *)WdLogNewEntry5_WdError();
      v6[3] = gCddImageInfo;
      v6[4] = (unsigned int)dword_14003E570;
      v6[5] = 215857758;
      WdLogGlobalForLineNumber = v5;
      goto LABEL_11;
    }
  }
  ViewSize[0] = 0;
  v7 = (PVOID *)((char *)a1 + 2552);
  v8 = MmMapViewInSessionSpace(*v2, (PVOID *)a1 + 319, ViewSize);
  if ( v8 >= 0 )
  {
    v10 = MmSizeOfMdl(*v7, *v3);
    Pool2 = ExAllocatePool2(64, v10, 1684300612);
    *((_QWORD *)a1 + 317) = Pool2;
    if ( Pool2 )
    {
      v12 = *v3;
      v13 = (unsigned __int64)*v7;
      *(_QWORD *)Pool2 = 0;
      *(_WORD *)(Pool2 + 8) = 8 * ((((v13 & 0xFFF) + v12 + 4095) >> 12) + 6);
      *(_WORD *)(Pool2 + 10) = 0;
      *(_QWORD *)(Pool2 + 32) = v13 & 0xFFFFFFFFFFFFF000uLL;
      *(_DWORD *)(Pool2 + 44) = v13 & 0xFFF;
      *(_DWORD *)(Pool2 + 40) = v12;
      MmProbeAndLockPages(*((PMDL *)a1 + 317), 0, IoModifyAccess);
      return;
    }
    WdLogSingleEntry2(2, a1, v10);
    v5 = 1725;
    goto LABEL_5;
  }
  WdLogSingleEntry3(2, a1, *v3, v8);
  WdLogGlobalForLineNumber = 1709;
  v9 = (_QWORD *)WdLogNewEntry5_WdError();
  v9[3] = gCddImageInfo;
  v9[4] = (unsigned int)dword_14003E570;
  v9[5] = 215857758;
  WdLogGlobalForLineNumber = 1709;
  v21 = 0;
  v17[0] = 6;
  v17[1] = 64;
  v20 = 0;
  v18 = 0;
  v19 = 0;
  v22 = 54;
  v23 = *(_DWORD *)v3;
  v24 = 0;
  (*((void (__fastcall **)(_DWORD *))a1 + 41))(v17);
LABEL_11:
  CddFreeShadowSysMem(a1);
  if ( *((_QWORD *)a1 + 2) )
  {
    if ( (*((_DWORD *)a1 + 686) & 0x200) == 0 )
    {
      WdLogSingleEntry1(4, a1);
      WdLogGlobalForLineNumber = 1764;
      v14 = (_QWORD *)WdLogNewEntry5_WdEvent();
      v14[3] = gCddImageInfo;
      v14[4] = (unsigned int)dword_14003E570;
      v14[5] = 215857758;
      WdLogGlobalForLineNumber = 1764;
      *((_DWORD *)a1 + 686) |= 0x200u;
      TriggerGdiModeReset(a1, 50);
    }
  }
}

```

## disassembly

```asm
0x1400248f8  push    rbx
0x1400248fa  push    rsi
0x1400248fb  push    rdi
0x1400248fc  push    r12
0x1400248fe  push    r14
0x140024900  push    r15
0x140024902  sub     rsp, 0B8h
0x140024909  mov     rax, cs:__security_cookie
0x140024910  xor     rax, rsp
0x140024913  mov     [rsp+0E8h+var_48], rax
0x14002491b  mov     rbx, rcx
0x14002491e  mov     [rsp+0E8h+var_98], rcx
0x140024923  xor     edi, edi
0x140024925  cmp     [rcx+9E8h], rdi
0x14002492c  jnz     loc_140024C8C
0x140024932  lea     r14, [rcx+9F0h]
0x140024939  lea     rsi, [rcx+0A00h]
0x140024940  lea     r15d, [rdi+6]
0x140024944  cmp     [r14], rdi
0x140024947  jnz     loc_1400249E6
0x14002494d  mov     [rsp+0E8h+var_A4], edi
0x140024951  mov     eax, [rsi]
0x140024953  mov     [rsp+0E8h+var_A8], eax
0x140024957  mov     [rsp+0E8h+var_B0], rdi
0x14002495c  mov     [rsp+0E8h+var_B8], rdi
0x140024961  mov     [rsp+0E8h+var_C0], 8000000h
0x140024969  mov     [rsp+0E8h+var_C8], 4
0x140024971  lea     r9, [rsp+0E8h+var_A8]
0x140024976  xor     r8d, r8d
0x140024979  mov     edx, r15d
0x14002497c  mov     rcx, r14
0x14002497f  call    cs:__imp_MmCreateSection
0x140024986  nop     dword ptr [rax+rax+00h]
0x14002498b  test    eax, eax
0x14002498d  jns     short loc_1400249E6
0x14002498f  movsxd  r9, eax
0x140024992  mov     r8, [rsi]
0x140024995  mov     rdx, rbx
0x140024998  lea     ecx, [rdi+2]
0x14002499b  call    cs:__imp_WdLogSingleEntry3
0x1400249a2  nop     dword ptr [rax+rax+00h]
0x1400249a7  mov     esi, 69Fh
0x1400249ac  mov     cs:WdLogGlobalForLineNumber, esi
0x1400249b2  call    cs:__imp_WdLogNewEntry5_WdError
0x1400249b9  nop     dword ptr [rax+rax+00h]
0x1400249be  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400249c5  mov     [rax+18h], rcx
0x1400249c9  mov     ecx, cs:dword_14003E570
0x1400249cf  mov     [rax+20h], rcx
0x1400249d3  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x1400249db  mov     cs:WdLogGlobalForLineNumber, esi
0x1400249e1  jmp     loc_140024C10
0x1400249e6  mov     [rsp+0E8h+ViewSize], rdi
0x1400249eb  lea     r12, [rbx+9F8h]
0x1400249f2  lea     r8, [rsp+0E8h+ViewSize]; ViewSize
0x1400249f7  mov     rdx, r12; MappedBase
0x1400249fa  mov     rcx, [r14]; Section
0x1400249fd  call    cs:__imp_MmMapViewInSessionSpace
0x140024a04  nop     dword ptr [rax+rax+00h]
0x140024a09  mov     rdx, [rsi]; Length
0x140024a0c  test    eax, eax
0x140024a0e  jns     loc_140024AC9
0x140024a14  movsxd  r9, eax
0x140024a17  mov     r8, rdx
0x140024a1a  mov     rdx, rbx
0x140024a1d  mov     ecx, 2
0x140024a22  call    cs:__imp_WdLogSingleEntry3
0x140024a29  nop     dword ptr [rax+rax+00h]
0x140024a2e  mov     r14d, 6ADh
0x140024a34  mov     cs:WdLogGlobalForLineNumber, r14d
0x140024a3b  call    cs:__imp_WdLogNewEntry5_WdError
0x140024a42  nop     dword ptr [rax+rax+00h]
0x140024a47  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140024a4e  mov     [rax+18h], rcx
0x140024a52  mov     ecx, cs:dword_14003E570
0x140024a58  mov     [rax+20h], rcx
0x140024a5c  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140024a64  mov     cs:WdLogGlobalForLineNumber, r14d
0x140024a6b  xorps   xmm0, xmm0
0x140024a6e  mov     [rsp+0E8h+var_60], rdi
0x140024a76  mov     [rsp+0E8h+var_88], r15d
0x140024a7b  mov     [rsp+0E8h+var_84], 40h ; '@'
0x140024a83  mov     [rsp+0E8h+var_68], rdi
0x140024a8b  xor     eax, eax
0x140024a8d  mov     [rsp+0E8h+var_80], rax
0x140024a92  movups  [rsp+0E8h+var_78], xmm0
0x140024a97  mov     [rsp+0E8h+var_58], 36h ; '6'
0x140024aa2  mov     eax, [rsi]
0x140024aa4  mov     [rsp+0E8h+var_54], eax
0x140024aab  mov     [rsp+0E8h+var_50], rdi
0x140024ab3  mov     rax, [rbx+148h]
0x140024aba  lea     rcx, [rsp+0E8h+var_88]
0x140024abf  call    _guard_dispatch_icall
0x140024ac4  jmp     loc_140024C10
0x140024ac9  mov     rcx, [r12]; Base
0x140024acd  call    cs:__imp_MmSizeOfMdl
0x140024ad4  nop     dword ptr [rax+rax+00h]
0x140024ad9  mov     r14, rax
0x140024adc  mov     r8d, 64646344h
0x140024ae2  mov     rdx, rax
0x140024ae5  mov     ecx, 40h ; '@'
0x140024aea  call    cs:__imp_ExAllocatePool2
0x140024af1  nop     dword ptr [rax+rax+00h]
0x140024af6  mov     r10, rax
0x140024af9  mov     [rbx+9E8h], rax
0x140024b00  test    rax, rax
0x140024b03  jnz     short loc_140024B24
0x140024b05  mov     r8, r14
0x140024b08  mov     rdx, rbx
0x140024b0b  lea     ecx, [rax+2]
0x140024b0e  call    cs:__imp_WdLogSingleEntry2
0x140024b15  nop     dword ptr [rax+rax+00h]
0x140024b1a  mov     esi, 6BDh
0x140024b1f  jmp     loc_1400249AC
0x140024b24  mov     r9, [rsi]
0x140024b27  mov     rdx, [r12]
0x140024b2b  mov     [rax], rdi
0x140024b2e  mov     r8d, edx
0x140024b31  mov     eax, r8d
0x140024b34  mov     r11d, 0FFFh
0x140024b3a  and     rax, r11
0x140024b3d  lea     rcx, [r9+0FFFh]
0x140024b44  add     rcx, rax
0x140024b47  shr     rcx, 0Ch
0x140024b4b  add     cx, r15w
0x140024b4f  shl     cx, 3
0x140024b53  mov     [r10+8], cx
0x140024b58  mov     [r10+0Ah], di
0x140024b5d  and     rdx, 0FFFFFFFFFFFFF000h
0x140024b64  mov     [r10+20h], rdx
0x140024b68  and     r8d, r11d
0x140024b6b  mov     [r10+2Ch], r8d
0x140024b6f  mov     [r10+28h], r9d
0x140024b73  xor     edx, edx; AccessMode
0x140024b75  lea     r8d, [rdx+2]; Operation
0x140024b79  mov     rcx, [rbx+9E8h]; MemoryDescriptorList
0x140024b80  call    cs:__imp_MmProbeAndLockPages
0x140024b87  nop     dword ptr [rax+rax+00h]
0x140024b8c  jmp     loc_140024C8C
0x140024b91  mov     rbx, [rsp+0E8h+var_98]
0x140024b96  mov     r8, [rbx+0A00h]
0x140024b9d  mov     rdx, rbx
0x140024ba0  mov     ecx, 2
0x140024ba5  call    cs:__imp_WdLogSingleEntry2
0x140024bac  nop     dword ptr [rax+rax+00h]
0x140024bb1  mov     cs:WdLogGlobalForLineNumber, 6CBh
0x140024bbb  call    cs:__imp_WdLogNewEntry5_WdError
0x140024bc2  nop     dword ptr [rax+rax+00h]
0x140024bc7  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140024bce  mov     [rax+18h], rcx
0x140024bd2  mov     ecx, cs:dword_14003E570
0x140024bd8  mov     [rax+20h], rcx
0x140024bdc  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140024be4  mov     cs:WdLogGlobalForLineNumber, 6CBh
0x140024bee  xor     edx, edx; Tag
0x140024bf0  mov     rcx, [rbx+9E8h]; P
0x140024bf7  call    cs:__imp_ExFreePoolWithTag
0x140024bfe  nop     dword ptr [rax+rax+00h]
0x140024c03  mov     qword ptr [rbx+9E8h], 0
0x140024c0e  xor     edi, edi
0x140024c10  mov     rcx, rbx; struct CDDPDEV *
0x140024c13  call    ?CddFreeShadowSysMem@@YAXPEAUCDDPDEV@@@Z; CddFreeShadowSysMem(CDDPDEV *)
0x140024c18  cmp     [rbx+10h], rdi
0x140024c1c  jz      short loc_140024C8C
0x140024c1e  mov     esi, 200h
0x140024c23  test    [rbx+0AB8h], esi
0x140024c29  jnz     short loc_140024C8C
0x140024c2b  mov     rdx, rbx
0x140024c2e  mov     ecx, 4
0x140024c33  call    cs:__imp_WdLogSingleEntry1
0x140024c3a  nop     dword ptr [rax+rax+00h]
0x140024c3f  mov     edi, 6E4h
0x140024c44  mov     cs:WdLogGlobalForLineNumber, edi
0x140024c4a  call    cs:__imp_WdLogNewEntry5_WdEvent
0x140024c51  nop     dword ptr [rax+rax+00h]
0x140024c56  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140024c5d  mov     [rax+18h], rcx
0x140024c61  mov     ecx, cs:dword_14003E570
0x140024c67  mov     [rax+20h], rcx
0x140024c6b  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140024c73  mov     cs:WdLogGlobalForLineNumber, edi
0x140024c79  or      [rbx+0AB8h], esi
0x140024c7f  mov     edx, 32h ; '2'
0x140024c84  mov     rcx, rbx
0x140024c87  call    ?TriggerGdiModeReset@@YAXPEAUCDDPDEV@@W4_DXGK_DIAG_CODE_POINT_TYPE@@@Z; TriggerGdiModeReset(CDDPDEV *,_DXGK_DIAG_CODE_POINT_TYPE)
0x140024c8c  mov     rcx, [rsp+0E8h+var_48]
0x140024c94  xor     rcx, rsp; StackCookie
0x140024c97  call    __security_check_cookie
0x140024c9c  add     rsp, 0B8h
0x140024ca3  pop     r15
0x140024ca5  pop     r14
0x140024ca7  pop     r12
0x140024ca9  pop     rdi
0x140024caa  pop     rsi
0x140024cab  pop     rbx
0x140024cac  retn
```
