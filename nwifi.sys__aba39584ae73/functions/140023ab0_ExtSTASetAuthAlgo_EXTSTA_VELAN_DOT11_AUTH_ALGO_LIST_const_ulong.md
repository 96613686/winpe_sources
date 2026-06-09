# ExtSTASetAuthAlgo(EXTSTA_VELAN *,_DOT11_AUTH_ALGO_LIST const *,ulong)

- ea: `0x140023ab0`
- end: `0x140023d75`
- name: `?ExtSTASetAuthAlgo@@YAJPEAUEXTSTA_VELAN@@PEBU_DOT11_AUTH_ALGO_LIST@@K@Z`
- size: `709`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *, const struct _DOT11_AUTH_ALGO_LIST *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x14000a238`
- `0x140019bbc`
- `0x140020dc0`
- `0x140020f20`
- `0x140023ab0`
- `0x140023d7c`
- `0x140065928`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140023bbe`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140023bbe`
- `ntoskrnl!ExAllocatePool2` at `0x140023bd3`
- `ntoskrnl!ExAllocatePool2` at `0x140023bd3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140023d38`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140023d38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023d49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023d49`

## pseudocode

```c
__int64 __fastcall ExtSTASetAuthAlgo(struct EXTSTA_VELAN *a1, const struct _DOT11_AUTH_ALGO_LIST *a2, int a3)
{
  unsigned int v3; // r9d
  unsigned int v6; // edx
  __int64 v7; // r11
  __int64 v8; // r10
  __int64 i; // r8
  int v10; // ebx
  unsigned int v11; // r14d
  unsigned int v12; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  __int64 v15; // r8
  _DWORD *j; // rdi
  unsigned int v17; // eax
  int v18; // edx
  __int64 v19; // r9
  int v20; // ecx
  __int64 v21; // rax
  unsigned int v22; // esi

  v3 = *(_DWORD *)a2;
  if ( (a3 - 8) / 0xCu < *(_DWORD *)a2 )
    return (unsigned int)-1073741789;
  if ( v3 != *((_DWORD *)a2 + 1) || !v3 )
    return (unsigned int)-1073741811;
  v6 = 0;
  v7 = 1928;
  v8 = 1936;
  if ( a1->Rw.DesiredBSSType != dot11_BSS_type_infrastructure )
  {
    v7 = 2040;
    v8 = 2048;
  }
LABEL_6:
  if ( v6 < v3 )
  {
    for ( i = 0; (unsigned int)i < *(unsigned int *)((char *)&a1->ModuleStatus.uValue + v7); i = (unsigned int)(i + 1) )
    {
      if ( *(_DWORD *)(*(_QWORD *)((char *)&a1->ModuleStatus.0 + v8) + 4 * i) == *((_DWORD *)a2 + 3 * v6 + 3) )
      {
        ++v6;
        goto LABEL_6;
      }
    }
    return (unsigned int)-1073741811;
  }
  Dot11RsnaOnSetAuthAlgo(a1->pGenVElan, a2);
  v11 = 4 * *(_DWORD *)a2 + 12;
  v12 = 4 * *(_DWORD *)a2 + 28;
  if ( v12 < 0x10 )
    return (unsigned int)-1073741670;
  if ( v12 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_22:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_24;
  }
  if ( v12 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_22;
  }
  if ( v12 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_22;
  }
  if ( v12 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_22;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v12, 808464432);
LABEL_24:
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  Pool2[2] = 808464432;
  v15 = 0;
  *(_QWORD *)Pool2 = p_DeviceQueue;
  for ( j = Pool2 + 4; (unsigned int)v15 < *(_DWORD *)a2; v15 = (unsigned int)(v15 + 1) )
    j[v15 + 3] = *((_DWORD *)a2 + 3 * v15 + 3);
  *j = 1048960;
  v17 = *(_DWORD *)a2;
  j[2] = *(_DWORD *)a2;
  j[1] = v17;
  v10 = PtRequestAdapterSync(a1->pGenVElan->pAdapt, 1u, 0xE010185u, j, v11);
  if ( v10 >= 0 )
  {
    v19 = (unsigned int)j[2];
    if ( (_DWORD)v19 == 1 )
    {
      v20 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          49,
          WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids,
          (unsigned int)j[3]);
    }
    else
    {
      v20 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids, v19);
        v21 = 0;
        if ( j[2] )
        {
          do
          {
            v20 = (int)WPP_GLOBAL_Control;
            v22 = v21 + 1;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              WPP_SF_Dd(
                WPP_GLOBAL_Control->AttachedDevice,
                51,
                WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids,
                v22,
                j[v21 + 3]);
            v21 = v22;
          }
          while ( v22 < j[2] );
        }
      }
    }
    if ( (byte_1400B2801 & 1) != 0 )
      McTemplateK0pjqQR2_EtwWriteTransfer(
        v20,
        v18,
        &a1->pGenVElan->gDeviceId,
        a1->pGenVElan,
        (__int64)&a1->pGenVElan->gDeviceId,
        j[1],
        (__int64)(j + 3));
    v10 = ExtSTAQueryRwParams(a1);
  }
  if ( j )
  {
    if ( *((_QWORD *)j - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)j - 2), j - 4);
    else
      ExFreePoolWithTag(j - 4, *(j - 2));
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140023ab0  push    rbx
0x140023ab2  push    rbp
0x140023ab3  push    rsi
0x140023ab4  push    rdi
0x140023ab5  push    r12
0x140023ab7  push    r13
0x140023ab9  push    r14
0x140023abb  sub     rsp, 40h
0x140023abf  mov     r9d, [rdx]
0x140023ac2  add     r8d, 0FFFFFFF8h
0x140023ac6  mov     rsi, rdx
0x140023ac9  mov     rax, 0AAAAAAAAAAAAAAABh
0x140023ad3  mul     r8
0x140023ad6  mov     rbp, rcx
0x140023ad9  shr     rdx, 3
0x140023add  cmp     edx, r9d
0x140023ae0  jb      loc_140023D5E
0x140023ae6  cmp     r9d, [rsi+4]
0x140023aea  jnz     short loc_140023B43
0x140023aec  test    r9d, r9d
0x140023aef  jz      short loc_140023B43
0x140023af1  mov     ecx, 7F8h
0x140023af6  xor     edx, edx
0x140023af8  cmp     dword ptr [rbp+6BCh], 1
0x140023aff  lea     r11d, [rcx-70h]
0x140023b03  lea     r10d, [rcx-68h]
0x140023b07  cmovnz  r11d, ecx
0x140023b0b  lea     r12d, [rcx+8]
0x140023b0f  cmovnz  r10d, r12d
0x140023b13  cmp     edx, r9d
0x140023b16  jnb     short loc_140023B4D
0x140023b18  mov     ebx, [r11+rbp]
0x140023b1c  mov     eax, edx
0x140023b1e  inc     rax
0x140023b21  xor     r8d, r8d
0x140023b24  lea     rax, [rax+rax*2]
0x140023b28  mov     edi, [rsi+rax*4]
0x140023b2b  cmp     r8d, ebx
0x140023b2e  jnb     short loc_140023B43
0x140023b30  mov     rax, [r10+rbp]
0x140023b34  cmp     [rax+r8*4], edi
0x140023b38  jz      short loc_140023B3F
0x140023b3a  inc     r8d
0x140023b3d  jmp     short loc_140023B2B
0x140023b3f  inc     edx
0x140023b41  jmp     short loc_140023B13
0x140023b43  mov     ebx, 0C000000Dh
0x140023b48  jmp     loc_140023D63
0x140023b4d  mov     rcx, [rbp+0A38h]; struct _VELAN *
0x140023b54  mov     rdx, rsi; struct _DOT11_AUTH_ALGO_LIST *
0x140023b57  call    ?Dot11RsnaOnSetAuthAlgo@@YAXPEAU_VELAN@@PEBU_DOT11_AUTH_ALGO_LIST@@@Z; Dot11RsnaOnSetAuthAlgo(_VELAN *,_DOT11_AUTH_ALGO_LIST const *)
0x140023b5c  mov     eax, [rsi]
0x140023b5e  mov     r13d, 10h
0x140023b64  lea     r14d, ds:0Ch[rax*4]
0x140023b6c  lea     eax, [r14+10h]
0x140023b70  cmp     eax, r13d
0x140023b73  jb      loc_140023D57
0x140023b79  lea     ecx, [r13+30h]
0x140023b7d  mov     edi, 30303030h
0x140023b82  cmp     eax, ecx
0x140023b84  ja      short loc_140023B8F
0x140023b86  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140023b8d  jmp     short loc_140023BBB
0x140023b8f  cmp     eax, 100h
0x140023b94  ja      short loc_140023B9F
0x140023b96  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140023b9d  jmp     short loc_140023BBB
0x140023b9f  cmp     eax, 400h
0x140023ba4  ja      short loc_140023BAF
0x140023ba6  lea     rbx, Lookaside
0x140023bad  jmp     short loc_140023BBB
0x140023baf  cmp     eax, r12d
0x140023bb2  ja      short loc_140023BCC
0x140023bb4  lea     rbx, stru_1400B31C0
0x140023bbb  mov     rcx, rbx; Lookaside
0x140023bbe  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140023bc5  nop     dword ptr [rax+rax+00h]
0x140023bca  jmp     short loc_140023BDF
0x140023bcc  xor     ebx, ebx
0x140023bce  mov     edx, eax
0x140023bd0  mov     r8d, edi
0x140023bd3  call    cs:__imp_ExAllocatePool2
0x140023bda  nop     dword ptr [rax+rax+00h]
0x140023bdf  test    rax, rax
0x140023be2  jz      loc_140023D57
0x140023be8  mov     [rax+8], edi
0x140023beb  xor     r8d, r8d
0x140023bee  mov     [rax], rbx
0x140023bf1  lea     rdi, [rax+10h]
0x140023bf5  cmp     [rsi], r8d
0x140023bf8  jbe     short loc_140023C0F
0x140023bfa  lea     rax, [r8+r8*2]
0x140023bfe  mov     ecx, [rsi+rax*4+0Ch]
0x140023c02  mov     [rdi+r8*4+0Ch], ecx
0x140023c07  inc     r8d
0x140023c0a  cmp     r8d, [rsi]
0x140023c0d  jb      short loc_140023BFA
0x140023c0f  mov     dword ptr [rdi], 100180h
0x140023c15  mov     r9, rdi; void *
0x140023c18  mov     eax, [rsi]
0x140023c1a  mov     edx, 1; unsigned int
0x140023c1f  mov     [rdi+8], eax
0x140023c22  mov     r8d, 0E010185h; unsigned int
0x140023c28  mov     [rdi+4], eax
0x140023c2b  mov     rcx, [rbp+0A38h]
0x140023c32  mov     [rsp+78h+var_58], r14d; unsigned int
0x140023c37  mov     rcx, [rcx+10h]; struct _ADAPT *
0x140023c3b  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x140023c40  mov     ebx, eax
0x140023c42  test    eax, eax
0x140023c44  js      loc_140023D21
0x140023c4a  mov     r9d, [rdi+8]
0x140023c4e  cmp     r9d, 1
0x140023c52  jnz     short loc_140023C81
0x140023c54  mov     rcx, cs:WPP_GLOBAL_Control
0x140023c5b  lea     rbx, WPP_GLOBAL_Control
0x140023c62  cmp     rcx, rbx
0x140023c65  jz      short loc_140023CE6
0x140023c67  mov     rcx, [rcx+18h]
0x140023c6b  lea     edx, [r9+30h]
0x140023c6f  mov     r9d, [rdi+0Ch]
0x140023c73  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x140023c7a  call    WPP_SF_d
0x140023c7f  jmp     short loc_140023CE6
0x140023c81  mov     rcx, cs:WPP_GLOBAL_Control
0x140023c88  lea     rbx, WPP_GLOBAL_Control
0x140023c8f  cmp     rcx, rbx
0x140023c92  jz      short loc_140023CE6
0x140023c94  mov     rcx, [rcx+18h]
0x140023c98  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x140023c9f  mov     edx, 32h ; '2'
0x140023ca4  call    WPP_SF_d
0x140023ca9  xor     eax, eax
0x140023cab  cmp     [rdi+8], eax
0x140023cae  jbe     short loc_140023CE6
0x140023cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x140023cb7  lea     esi, [rax+1]
0x140023cba  cmp     rcx, rbx
0x140023cbd  jz      short loc_140023CDF
0x140023cbf  mov     eax, [rdi+rax*4+0Ch]
0x140023cc3  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x140023cca  mov     rcx, [rcx+18h]
0x140023cce  mov     edx, 33h ; '3'
0x140023cd3  mov     r9d, esi
0x140023cd6  mov     [rsp+78h+var_58], eax
0x140023cda  call    WPP_SF_Dd
0x140023cdf  mov     eax, esi
0x140023ce1  cmp     eax, [rdi+8]
0x140023ce4  jb      short loc_140023CB0
0x140023ce6  test    cs:byte_1400B2801, 1
0x140023ced  jz      short loc_140023D17
0x140023cef  mov     r9, [rbp+0A38h]
0x140023cf6  lea     rax, [rdi+0Ch]
0x140023cfa  mov     [rsp+78h+var_48], rax
0x140023cff  mov     eax, [rdi+4]
0x140023d02  mov     [rsp+78h+var_50], eax
0x140023d06  lea     r8, [r9+1338h]
0x140023d0d  mov     qword ptr [rsp+78h+var_58], r8
0x140023d12  call    McTemplateK0pjqQR2_EtwWriteTransfer
0x140023d17  mov     rcx, rbp; struct EXTSTA_VELAN *
0x140023d1a  call    ?ExtSTAQueryRwParams@@YAHPEAUEXTSTA_VELAN@@@Z; ExtSTAQueryRwParams(EXTSTA_VELAN *)
0x140023d1f  mov     ebx, eax
0x140023d21  test    rdi, rdi
0x140023d24  jz      short loc_140023D63
0x140023d26  lea     rcx, [rdi-10h]; P
0x140023d2a  mov     rax, [rcx]
0x140023d2d  test    rax, rax
0x140023d30  jz      short loc_140023D46
0x140023d32  mov     rdx, rcx; Entry
0x140023d35  mov     rcx, rax; Lookaside
0x140023d38  call    cs:__imp_ExFreeToNPagedLookasideList
0x140023d3f  nop     dword ptr [rax+rax+00h]
0x140023d44  jmp     short loc_140023D63
0x140023d46  mov     edx, [rcx+8]; Tag
0x140023d49  call    cs:__imp_ExFreePoolWithTag
0x140023d50  nop     dword ptr [rax+rax+00h]
0x140023d55  jmp     short loc_140023D63
0x140023d57  mov     ebx, 0C000009Ah
0x140023d5c  jmp     short loc_140023D63
0x140023d5e  mov     ebx, 0C0000023h
0x140023d63  mov     eax, ebx
0x140023d65  add     rsp, 40h
0x140023d69  pop     r14
0x140023d6b  pop     r13
0x140023d6d  pop     r12
0x140023d6f  pop     rdi
0x140023d70  pop     rsi
0x140023d71  pop     rbp
0x140023d72  pop     rbx
0x140023d73  retn
```
