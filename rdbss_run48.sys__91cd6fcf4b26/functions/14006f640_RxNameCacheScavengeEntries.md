# RxNameCacheScavengeEntries

- ea: `0x14006f640`
- end: `0x14006f960`
- name: `RxNameCacheScavengeEntries`
- size: `800`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140014e40`
- `0x140025d00`
- `0x14006f640`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006f780`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f799`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f8a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f8bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f780`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f799`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f8a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f8bb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006f672`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006f6ed`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006f672`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006f6ed`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006f6c6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006f8ea`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006f6c6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006f8ea`

## pseudocode

```c
__int64 __fastcall RxNameCacheScavengeEntries(__int64 *a1)
{
  unsigned int v2; // r13d
  __int64 *v3; // rbx
  __int64 *v4; // rdi
  _QWORD **v6; // r15
  unsigned int v7; // edx
  unsigned int v8; // r14d
  int v9; // r14d
  _QWORD *v10; // rax
  _QWORD *v11; // rcx
  _QWORD *v12; // rbp
  void *v13; // rcx
  _QWORD *v14; // rax
  _QWORD *v15; // rbp
  __int64 v16; // rcx
  _QWORD *v17; // rdx
  _QWORD *v18; // rax
  __int64 v19; // rdx
  _QWORD *v20; // rcx
  void (__fastcall *v21)(__int64, _QWORD *); // rax
  void *v22; // rcx
  unsigned __int64 v23; // [rsp+78h] [rbp+10h]

  v2 = 0;
  v23 = MEMORY[0xFFFFF78000000008];
  ExAcquirePushLockExclusiveEx(&RxNameCacheGlobalConfig, 0);
  v3 = (__int64 *)qword_140038AC8;
  while ( v3 != &qword_140038AC8 )
  {
    v4 = v3 - 4;
    v3 = (__int64 *)*v3;
    if ( (!a1 || a1 == v4) && *((_DWORD *)v4 + 22) > *((_DWORD *)v4 + 23) )
    {
      ExAcquirePushLockExclusiveEx(v4 + 6, 0);
      v6 = (_QWORD **)(v4 + 9);
      v7 = *((_DWORD *)v4 + 23);
      v8 = *((_DWORD *)v4 + 22) - v7;
      if ( *((_DWORD *)v4 + 22) <= v7 )
        v8 = 0;
      v9 = (v8 >> 2) + 1;
      do
      {
        v10 = *v6;
        if ( *v6 == v6 )
          break;
        if ( (_QWORD **)v10[1] != v6 || (v11 = (_QWORD *)*v10, *(_QWORD **)(*v10 + 8LL) != v10) )
LABEL_32:
          __fastfail(3u);
        *v6 = v11;
        v12 = v10 - 8;
        v11[1] = v6;
        v10[1] = v10;
        *v10 = v10;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 26, &WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids, v12 + 10);
        }
        v13 = (void *)v12[11];
        if ( v13 )
        {
          ExFreePoolWithTag(v13, 0);
          v12[11] = 0;
        }
        ExFreePoolWithTag(v12, 0);
        _InterlockedDecrement((volatile signed __int32 *)v4 + 22);
        ++v2;
        _InterlockedDecrement(&dword_140038AD8);
        --v9;
      }
      while ( v9 );
      while ( v9 )
      {
        if ( (__int64 *)v4[7] == v4 + 7 )
          break;
        v14 = (_QWORD *)v4[8];
        v15 = v14 - 8;
        if ( v23 < *(v14 - 1) )
          break;
        v16 = *v14;
        if ( *(_QWORD **)(*v14 + 8LL) != v14 )
          goto LABEL_32;
        v17 = (_QWORD *)v14[1];
        if ( (_QWORD *)*v17 != v14 )
          goto LABEL_32;
        *v17 = v16;
        *(_QWORD *)(v16 + 8) = v17;
        v14[1] = v14;
        *v14 = v14;
        v18 = v15 + 12;
        v19 = v15[12];
        if ( *(_QWORD **)(v19 + 8) != v15 + 12 )
          goto LABEL_32;
        v20 = (_QWORD *)v15[13];
        if ( (_QWORD *)*v20 != v18 )
          goto LABEL_32;
        *v20 = v19;
        *(_QWORD *)(v19 + 8) = v20;
        v15[13] = v18;
        *v18 = v18;
        if ( *(_WORD *)v15 != 0xEBAA )
        {
          v21 = (void (__fastcall *)(__int64, _QWORD *))v4[17];
          if ( v21 )
          {
            v21(v4[18], v15);
            v15[5] = 0;
          }
          _InterlockedDecrement((volatile signed __int32 *)v4 + 25);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 26, &WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids, v15 + 10);
          }
          v22 = (void *)v15[11];
          if ( v22 )
          {
            ExFreePoolWithTag(v22, 0);
            v15[11] = 0;
          }
          ExFreePoolWithTag(v15, 0);
          _InterlockedDecrement((volatile signed __int32 *)v4 + 22);
          --v9;
          _InterlockedDecrement(&dword_140038AD8);
          ++v2;
        }
      }
      ExReleasePushLockExclusiveEx(v4 + 6, 0);
    }
  }
  ExReleasePushLockExclusiveEx(&RxNameCacheGlobalConfig, 0);
  return v2;
}

```

## disassembly

```asm
0x14006f640  push    rbx
0x14006f642  push    rbp
0x14006f643  push    rsi
0x14006f644  push    rdi
0x14006f645  push    r12
0x14006f647  push    r13
0x14006f649  push    r14
0x14006f64b  push    r15
0x14006f64d  sub     rsp, 28h
0x14006f651  mov     rsi, rcx
0x14006f654  mov     rax, 0FFFFF78000000008h
0x14006f65e  xor     edx, edx
0x14006f660  lea     rcx, RxNameCacheGlobalConfig
0x14006f667  xor     r13d, r13d
0x14006f66a  mov     rax, [rax]
0x14006f66d  mov     [rsp+68h+arg_8], rax
0x14006f672  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006f679  nop     dword ptr [rax+rax+00h]
0x14006f67e  mov     rbx, cs:qword_140038AC8
0x14006f685  lea     rcx, qword_140038AC8
0x14006f68c  cmp     rbx, rcx
0x14006f68f  jz      short loc_14006F6BD
0x14006f691  nop     dword ptr [rax+00h]
0x14006f695  nop     word ptr [rax+rax+00000000h]
0x14006f6a0  lea     rdi, [rbx-20h]
0x14006f6a4  mov     rbx, [rbx]
0x14006f6a7  test    rsi, rsi
0x14006f6aa  jnz     loc_14006F902
0x14006f6b0  mov     eax, [rdi+5Ch]
0x14006f6b3  cmp     [rdi+58h], eax
0x14006f6b6  ja      short loc_14006F6E7
0x14006f6b8  cmp     rbx, rcx
0x14006f6bb  jnz     short loc_14006F6A0
0x14006f6bd  xor     edx, edx
0x14006f6bf  lea     rcx, RxNameCacheGlobalConfig
0x14006f6c6  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006f6cd  nop     dword ptr [rax+rax+00h]
0x14006f6d2  mov     eax, r13d
0x14006f6d5  add     rsp, 28h
0x14006f6d9  pop     r15
0x14006f6db  pop     r14
0x14006f6dd  pop     r13
0x14006f6df  pop     r12
0x14006f6e1  pop     rdi
0x14006f6e2  pop     rsi
0x14006f6e3  pop     rbp
0x14006f6e4  pop     rbx
0x14006f6e5  retn
0x14006f6e7  xor     edx, edx
0x14006f6e9  lea     rcx, [rdi+30h]
0x14006f6ed  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006f6f4  nop     dword ptr [rax+rax+00h]
0x14006f6f9  mov     ecx, [rdi+58h]
0x14006f6fc  lea     r15, [rdi+48h]
0x14006f700  mov     edx, [rdi+5Ch]
0x14006f703  xor     eax, eax
0x14006f705  mov     r14d, ecx
0x14006f708  sub     r14d, edx
0x14006f70b  cmp     ecx, edx
0x14006f70d  cmovbe  r14d, eax
0x14006f711  shr     r14d, 2
0x14006f715  inc     r14d
0x14006f718  nop     dword ptr [rax+rax+00000000h]
0x14006f720  mov     rax, [r15]
0x14006f723  cmp     rax, r15
0x14006f726  jz      loc_14006F7C0
0x14006f72c  cmp     [rax+8], r15
0x14006f730  jnz     loc_14006F8DD
0x14006f736  mov     rcx, [rax]
0x14006f739  cmp     [rcx+8], rax
0x14006f73d  jnz     loc_14006F8DD
0x14006f743  mov     [r15], rcx
0x14006f746  lea     rbp, [rax-40h]
0x14006f74a  mov     [rcx+8], r15
0x14006f74e  mov     [rax+8], rax
0x14006f752  mov     [rax], rax
0x14006f755  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f75c  lea     rax, WPP_GLOBAL_Control
0x14006f763  cmp     rcx, rax
0x14006f766  jz      short loc_14006F775
0x14006f768  test    dword ptr [rcx+2Ch], 800h
0x14006f76f  jnz     loc_14006F910
0x14006f775  mov     rcx, [rbp+58h]; P
0x14006f779  test    rcx, rcx
0x14006f77c  jz      short loc_14006F794
0x14006f77e  xor     edx, edx; Tag
0x14006f780  call    cs:__imp_ExFreePoolWithTag
0x14006f787  nop     dword ptr [rax+rax+00h]
0x14006f78c  mov     qword ptr [rbp+58h], 0
0x14006f794  xor     edx, edx; Tag
0x14006f796  mov     rcx, rbp; P
0x14006f799  call    cs:__imp_ExFreePoolWithTag
0x14006f7a0  nop     dword ptr [rax+rax+00h]
0x14006f7a5  lock dec dword ptr [rdi+58h]
0x14006f7a9  inc     r13d
0x14006f7ac  lock dec cs:dword_140038AD8
0x14006f7b3  add     r14d, 0FFFFFFFFh
0x14006f7b7  jnz     loc_14006F720
0x14006f7bd  nop     dword ptr [rax]
0x14006f7c0  test    r14d, r14d
0x14006f7c3  jz      loc_14006F8E4
0x14006f7c9  lea     rax, [rdi+38h]
0x14006f7cd  cmp     [rax], rax
0x14006f7d0  jz      loc_14006F8E4
0x14006f7d6  mov     rax, [rdi+40h]
0x14006f7da  mov     rcx, [rsp+68h+arg_8]
0x14006f7df  lea     rbp, [rax-40h]
0x14006f7e3  cmp     rcx, [rbp+38h]
0x14006f7e7  jb      loc_14006F8E4
0x14006f7ed  mov     rcx, [rax]
0x14006f7f0  cmp     [rcx+8], rax
0x14006f7f4  jnz     loc_14006F8DD
0x14006f7fa  mov     rdx, [rax+8]
0x14006f7fe  cmp     [rdx], rax
0x14006f801  jnz     loc_14006F8DD
0x14006f807  mov     [rdx], rcx
0x14006f80a  mov     [rcx+8], rdx
0x14006f80e  mov     [rax+8], rax
0x14006f812  mov     [rax], rax
0x14006f815  lea     rax, [rbp+60h]
0x14006f819  mov     rdx, [rax]
0x14006f81c  cmp     [rdx+8], rax
0x14006f820  jnz     loc_14006F8DD
0x14006f826  mov     rcx, [rbp+68h]
0x14006f82a  cmp     [rcx], rax
0x14006f82d  jnz     loc_14006F8DD
0x14006f833  mov     [rcx], rdx
0x14006f836  mov     [rdx+8], rcx
0x14006f83a  mov     [rbp+68h], rax
0x14006f83e  mov     [rax], rax
0x14006f841  mov     eax, 0EBAAh
0x14006f846  cmp     [rbp+0], ax
0x14006f84a  jz      loc_14006F7C0
0x14006f850  mov     rax, [rdi+88h]
0x14006f857  test    rax, rax
0x14006f85a  jz      short loc_14006F873
0x14006f85c  mov     rcx, [rdi+90h]
0x14006f863  mov     rdx, rbp
0x14006f866  call    _guard_dispatch_icall
0x14006f86b  mov     qword ptr [rbp+28h], 0
0x14006f873  lock dec dword ptr [rdi+64h]
0x14006f877  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f87e  lea     rax, WPP_GLOBAL_Control
0x14006f885  cmp     rcx, rax
0x14006f888  jz      short loc_14006F897
0x14006f88a  test    dword ptr [rcx+2Ch], 800h
0x14006f891  jnz     loc_14006F938
0x14006f897  mov     rcx, [rbp+58h]; P
0x14006f89b  test    rcx, rcx
0x14006f89e  jz      short loc_14006F8B6
0x14006f8a0  xor     edx, edx; Tag
0x14006f8a2  call    cs:__imp_ExFreePoolWithTag
0x14006f8a9  nop     dword ptr [rax+rax+00h]
0x14006f8ae  mov     qword ptr [rbp+58h], 0
0x14006f8b6  xor     edx, edx; Tag
0x14006f8b8  mov     rcx, rbp; P
0x14006f8bb  call    cs:__imp_ExFreePoolWithTag
0x14006f8c2  nop     dword ptr [rax+rax+00h]
0x14006f8c7  lock dec dword ptr [rdi+58h]
0x14006f8cb  dec     r14d
0x14006f8ce  lock dec cs:dword_140038AD8
0x14006f8d5  inc     r13d
0x14006f8d8  jmp     loc_14006F7C0
0x14006f8dd  mov     ecx, 3
0x14006f8e2  int     29h; Win8: RtlFailFast(ecx)
0x14006f8e4  xor     edx, edx
0x14006f8e6  lea     rcx, [rdi+30h]
0x14006f8ea  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006f8f1  nop     dword ptr [rax+rax+00h]
0x14006f8f6  lea     rcx, qword_140038AC8
0x14006f8fd  jmp     loc_14006F6B8
0x14006f902  cmp     rsi, rdi
0x14006f905  jnz     loc_14006F6B8
0x14006f90b  jmp     loc_14006F6B0
0x14006f910  cmp     byte ptr [rcx+29h], 4
0x14006f914  jb      loc_14006F775
0x14006f91a  mov     rcx, [rcx+18h]
0x14006f91e  lea     r9, [rbp+50h]
0x14006f922  mov     edx, 1Ah
0x14006f927  lea     r8, WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids
0x14006f92e  call    WPP_SF_Z
0x14006f933  jmp     loc_14006F775
0x14006f938  cmp     byte ptr [rcx+29h], 4
0x14006f93c  jb      loc_14006F897
0x14006f942  mov     rcx, [rcx+18h]
0x14006f946  lea     r9, [rbp+50h]
0x14006f94a  mov     edx, 1Ah
0x14006f94f  lea     r8, WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids
0x14006f956  call    WPP_SF_Z
0x14006f95b  jmp     loc_14006F897
```
