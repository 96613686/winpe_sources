# VmbusRecvBuildIrp

- ea: `0x1400567cc`
- end: `0x14005696e`
- name: `VmbusRecvBuildIrp`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140056060`

## callees

- `0x140028960`
- `0x140038414`
- `0x14005540c`
- `0x1400567cc`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400568d8`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400568d8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14005686d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14005686d`
- `rdbss!RxAllocateMdl2` at `0x1400568b2`
- `rdbss!RxAllocateMdl2` at `0x1400568b2`

## pseudocode

```c
__int64 __fastcall VmbusRecvBuildIrp(_QWORD *a1)
{
  __int64 v1; // rbp
  __int64 v3; // rcx
  __int64 result; // rax
  __int64 v5; // rdi
  __int64 v6; // rax
  unsigned int v7; // ebx
  char *v8; // r14
  __int64 *v9; // rsi
  unsigned int v10; // r12d
  unsigned int v11; // ecx
  char *v12; // rax
  int v13; // edx
  struct _MDL *Mdl2; // rax
  struct _MDL *v15; // rsi
  __int64 v16; // rcx
  __int64 v17; // rax

  v1 = a1[16];
  v3 = a1[13];
  LOBYTE(v3) = *(_BYTE *)(v3 + 76);
  result = RxVmbusAllocateIrp(v3);
  v5 = result;
  if ( result )
  {
    if ( *(_DWORD *)(v1 + 8) )
    {
      v9 = *(__int64 **)(v1 + 32);
      v10 = 0;
      if ( v9 )
      {
        while ( 1 )
        {
          v11 = v10 + *((_DWORD *)v9 + 10);
          if ( *(_DWORD *)(v1 + 24) < v11 )
            break;
          v7 = 0;
          v8 = 0;
          v9 = (__int64 *)*v9;
          v10 = v11;
          if ( !v9 )
            goto LABEL_15;
        }
        if ( (*((_BYTE *)v9 + 10) & 5) != 0 )
          v12 = (char *)v9[3];
        else
          v12 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v9, 0, MmCached, 0, 0, 0x40000010u);
        v13 = *(_DWORD *)(v1 + 24);
        v8 = &v12[v13 - v10];
        v7 = v10 + *((_DWORD *)v9 + 10) - v13;
        if ( v7 >= *(_DWORD *)(v1 + 20) - v13 )
          v7 = *(_DWORD *)(v1 + 20) - v13;
      }
      else
      {
        v7 = 0;
        v8 = 0;
      }
    }
    else
    {
      v6 = *(unsigned int *)(v1 + 24);
      v7 = 4 - v6;
      v8 = (char *)(v6 + v1 + 12);
    }
LABEL_15:
    Mdl2 = (struct _MDL *)RxAllocateMdl2(v8, v7, 0, 0, 0);
    v15 = Mdl2;
    if ( Mdl2 )
    {
      MmBuildMdlForNonPagedPool(Mdl2);
      v16 = *(_QWORD *)(v5 + 184);
      *(_BYTE *)(v16 - 72) = 3;
      *(_DWORD *)(v16 - 64) = v7;
      *(_QWORD *)(v16 - 24) = a1[14];
      v17 = *(_QWORD *)(v5 + 184);
      *(_QWORD *)(v5 + 8) = v15;
      *(_QWORD *)(v17 - 16) = VmbusRecvAsyncCompletion;
      *(_QWORD *)(v17 - 8) = a1;
      *(_BYTE *)(v17 - 69) = -32;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids, v5, v8, v7);
      }
    }
    else
    {
      RxVmbusFreeIrp(v5);
      return 0;
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1400567cc  push    rbx
0x1400567ce  push    rbp
0x1400567cf  push    rsi
0x1400567d0  push    rdi
0x1400567d1  push    r12
0x1400567d3  push    r14
0x1400567d5  push    r15
0x1400567d7  sub     rsp, 30h
0x1400567db  mov     rbp, [rcx+80h]
0x1400567e2  mov     r15, rcx
0x1400567e5  mov     rcx, [rcx+68h]
0x1400567e9  mov     cl, [rcx+4Ch]
0x1400567ec  call    RxVmbusAllocateIrp
0x1400567f1  mov     rdi, rax
0x1400567f4  test    rax, rax
0x1400567f7  jz      loc_14005695E
0x1400567fd  cmp     dword ptr [rbp+8], 0
0x140056801  jnz     short loc_140056819
0x140056803  mov     eax, [rbp+18h]
0x140056806  lea     r14, [rbp+0Ch]
0x14005680a  mov     ebx, 4
0x14005680f  sub     ebx, eax
0x140056811  add     r14, rax
0x140056814  jmp     loc_14005689E
0x140056819  mov     rsi, [rbp+20h]
0x14005681d  xor     r12d, r12d
0x140056820  test    rsi, rsi
0x140056823  jz      short loc_140056899
0x140056825  mov     ecx, [rsi+28h]
0x140056828  add     ecx, r12d
0x14005682b  cmp     [rbp+18h], ecx
0x14005682e  jb      short loc_140056845
0x140056830  mov     rax, [rsi]
0x140056833  xor     ebx, ebx
0x140056835  xor     r14d, r14d
0x140056838  mov     rsi, rax
0x14005683b  mov     r12d, ecx
0x14005683e  test    rax, rax
0x140056841  jnz     short loc_140056825
0x140056843  jmp     short loc_14005689E
0x140056845  test    byte ptr [rsi+0Ah], 5
0x140056849  jz      short loc_140056851
0x14005684b  mov     rax, [rsi+18h]
0x14005684f  jmp     short loc_140056879
0x140056851  xor     r9d, r9d; RequestedAddress
0x140056854  mov     [rsp+68h+Priority], 40000010h; Priority
0x14005685c  xor     edx, edx; AccessMode
0x14005685e  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140056866  mov     rcx, rsi; MemoryDescriptorList
0x140056869  lea     r8d, [r9+1]; CacheType
0x14005686d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140056874  nop     dword ptr [rax+rax+00h]
0x140056879  mov     edx, [rbp+18h]
0x14005687c  mov     r14d, edx
0x14005687f  mov     ebx, [rsi+28h]
0x140056882  sub     r14d, r12d
0x140056885  add     r14, rax
0x140056888  sub     ebx, edx
0x14005688a  mov     eax, [rbp+14h]
0x14005688d  add     ebx, r12d
0x140056890  sub     eax, edx
0x140056892  cmp     ebx, eax
0x140056894  cmovnb  ebx, eax
0x140056897  jmp     short loc_14005689E
0x140056899  xor     ebx, ebx
0x14005689b  xor     r14d, r14d
0x14005689e  xor     r9d, r9d
0x1400568a1  mov     qword ptr [rsp+68h+BugCheckOnFailure], 0
0x1400568aa  xor     r8d, r8d
0x1400568ad  mov     edx, ebx
0x1400568af  mov     rcx, r14
0x1400568b2  call    cs:__imp_RxAllocateMdl2
0x1400568b9  nop     dword ptr [rax+rax+00h]
0x1400568be  mov     rsi, rax
0x1400568c1  test    rax, rax
0x1400568c4  jnz     short loc_1400568D5
0x1400568c6  mov     rcx, rdi
0x1400568c9  call    RxVmbusFreeIrp
0x1400568ce  xor     edi, edi
0x1400568d0  jmp     loc_14005695B
0x1400568d5  mov     rcx, rsi; MemoryDescriptorList
0x1400568d8  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400568df  nop     dword ptr [rax+rax+00h]
0x1400568e4  mov     rcx, [rdi+0B8h]
0x1400568eb  mov     byte ptr [rcx-48h], 3
0x1400568ef  mov     [rcx-40h], ebx
0x1400568f2  mov     rax, [r15+70h]
0x1400568f6  mov     [rcx-18h], rax
0x1400568fa  lea     rcx, VmbusRecvAsyncCompletion
0x140056901  mov     rax, [rdi+0B8h]
0x140056908  mov     [rdi+8], rsi
0x14005690c  mov     [rax-10h], rcx
0x140056910  mov     [rax-8], r15
0x140056914  mov     byte ptr [rax-45h], 0E0h
0x140056918  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005691f  lea     rax, WPP_GLOBAL_Control
0x140056926  cmp     rcx, rax
0x140056929  jz      short loc_14005695B
0x14005692b  test    dword ptr [rcx+2Ch], 200h
0x140056932  jz      short loc_14005695B
0x140056934  cmp     byte ptr [rcx+29h], 4
0x140056938  jb      short loc_14005695B
0x14005693a  mov     rcx, [rcx+18h]
0x14005693e  lea     r8, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids
0x140056945  mov     edx, 0Fh
0x14005694a  mov     [rsp+68h+Priority], ebx
0x14005694e  mov     r9, rdi
0x140056951  mov     qword ptr [rsp+68h+BugCheckOnFailure], r14
0x140056956  call    WPP_SF_qqD
0x14005695b  mov     rax, rdi
0x14005695e  add     rsp, 30h
0x140056962  pop     r15
0x140056964  pop     r14
0x140056966  pop     r12
0x140056968  pop     rdi
0x140056969  pop     rsi
0x14005696a  pop     rbp
0x14005696b  pop     rbx
0x14005696c  retn
```
