# CDetectionAndSharing::InitializeServiceStatusArray(void)

- ea: `0x180003410`
- end: `0x180003568`
- name: `?InitializeServiceStatusArray@CDetectionAndSharing@@AEAAJXZ`
- size: `344`
- prototype: `__int64 __fastcall(CDetectionAndSharing *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800025c8`
- `0x180002b64`

## callees

- `0x1800025a0`
- `0x180002fc4`
- `0x180003210`
- `0x180003310`
- `0x180003410`

## import_xrefs

- `msvcrt!free` at `0x18000342f`
- `msvcrt!free` at `0x180003473`
- `msvcrt!free` at `0x18000342f`
- `msvcrt!free` at `0x180003473`

## pseudocode

```c
__int64 __fastcall CDetectionAndSharing::InitializeServiceStatusArray(CDetectionAndSharing *this)
{
  __int64 *v1; // rbx
  void *v3; // rcx
  _QWORD *v4; // rdi
  void *v5; // rcx
  unsigned int i; // ebp
  __int64 v7; // rax
  __int64 v8; // r14
  unsigned __int64 v9; // rcx
  unsigned int v11; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v12; // [rsp+58h] [rbp+10h] BYREF

  v1 = (__int64 *)((char *)this + 80);
  v3 = (void *)*((_QWORD *)this + 10);
  if ( v3 )
  {
    free(v3);
    *v1 = 0;
  }
  v1[1] = 0;
  v1[2] = 0;
  if ( !ATL::CAtlArray<_ServiceStatus,ATL::CElementTraits<_ServiceStatus>>::GrowBuffer((__int64)v1, 6u) )
    return 2147942414LL;
  v1[1] = 6;
  v4 = (_QWORD *)((char *)this + 112);
  v5 = (void *)*((_QWORD *)this + 14);
  if ( v5 )
  {
    free(v5);
    *v4 = 0;
  }
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  if ( !(unsigned __int8)ATL::CAtlArray<_CategoryStatus,ATL::CElementTraits<_CategoryStatus>>::GrowBuffer(
                           (char *)this + 112,
                           5) )
    return 2147942414LL;
  *((_QWORD *)this + 15) = 5;
  for ( i = 0; (unsigned __int64)i < *((_QWORD *)this + 11); ++i )
  {
    if ( i >= (unsigned __int64)v1[1]
      || (v7 = *v1,
          v8 = 4LL * i,
          v11 = 0,
          v12 = 0,
          *(_OWORD *)(v8 * 8 + v7) = *(_OWORD *)&off_1800066A0[v8],
          *(_OWORD *)(v8 * 8 + v7 + 16) = *(_OWORD *)&off_1800066A0[v8 + 2],
          i >= (unsigned __int64)v1[1]) )
    {
LABEL_17:
      ATL::AtlThrowImpl(-2147024809);
    }
    if ( (int)CDetectionAndSharing::GetServiceInfo(this, *(const unsigned __int16 **)(v8 * 8 + *v1), &v11, &v12) < 0
      || v11 != 4 )
    {
      v9 = SLODWORD(off_1800066A0[v8 + 2]);
      if ( v9 >= *((_QWORD *)this + 15) )
        goto LABEL_17;
      ++*(_DWORD *)(*v4 + 8 * v9);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003410  mov     [rsp+arg_10], rbx
0x180003415  push    rbp
0x180003416  push    rsi
0x180003417  push    rdi
0x180003418  push    r12
0x18000341a  push    r14
0x18000341c  sub     rsp, 20h
0x180003420  lea     rbx, [rcx+50h]
0x180003424  mov     rsi, rcx
0x180003427  mov     rcx, [rbx]; Block
0x18000342a  test    rcx, rcx
0x18000342d  jz      short loc_18000343C
0x18000342f  call    cs:__imp_free
0x180003435  mov     qword ptr [rbx], 0
0x18000343c  mov     edi, 6
0x180003441  mov     qword ptr [rbx+8], 0
0x180003449  mov     edx, edi
0x18000344b  mov     qword ptr [rbx+10h], 0
0x180003453  mov     rcx, rbx
0x180003456  call    ?GrowBuffer@?$CAtlArray@U_ServiceStatus@@V?$CElementTraits@U_ServiceStatus@@@ATL@@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<_ServiceStatus,ATL::CElementTraits<_ServiceStatus>>::GrowBuffer(unsigned __int64)
0x18000345b  test    al, al
0x18000345d  jz      loc_180003547
0x180003463  mov     [rbx+8], rdi
0x180003467  lea     rdi, [rsi+70h]
0x18000346b  mov     rcx, [rdi]; Block
0x18000346e  test    rcx, rcx
0x180003471  jz      short loc_180003480
0x180003473  call    cs:__imp_free
0x180003479  mov     qword ptr [rdi], 0
0x180003480  mov     ebp, 5
0x180003485  mov     qword ptr [rdi+8], 0
0x18000348d  mov     edx, ebp
0x18000348f  mov     qword ptr [rdi+10h], 0
0x180003497  mov     rcx, rdi
0x18000349a  call    ?GrowBuffer@?$CAtlArray@U_CategoryStatus@@V?$CElementTraits@U_CategoryStatus@@@ATL@@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<_CategoryStatus,ATL::CElementTraits<_CategoryStatus>>::GrowBuffer(unsigned __int64)
0x18000349f  test    al, al
0x1800034a1  jz      loc_180003547
0x1800034a7  mov     [rdi+8], rbp
0x1800034ab  xor     ebp, ebp
0x1800034ad  cmp     [rsi+58h], rbp
0x1800034b1  jbe     loc_180003543
0x1800034b7  lea     r12, off_1800066A0; "lanmanserver"
0x1800034be  mov     ecx, ebp
0x1800034c0  cmp     rcx, [rbx+8]
0x1800034c4  jnb     loc_18000355D
0x1800034ca  mov     rax, [rbx]
0x1800034cd  mov     r14d, ecx
0x1800034d0  shl     r14, 5
0x1800034d4  mov     [rsp+48h+arg_0], 0
0x1800034dc  mov     [rsp+48h+arg_8], 0
0x1800034e4  movups  xmm0, xmmword ptr [r14+r12]
0x1800034e9  movups  xmmword ptr [r14+rax], xmm0
0x1800034ee  movups  xmm1, xmmword ptr [r14+r12+10h]
0x1800034f4  movups  xmmword ptr [r14+rax+10h], xmm1
0x1800034fa  cmp     rcx, [rbx+8]
0x1800034fe  jnb     short loc_18000355D
0x180003500  mov     rdx, [rbx]
0x180003503  lea     r9, [rsp+48h+arg_8]; unsigned int *
0x180003508  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x18000350d  mov     rcx, rsi; this
0x180003510  mov     rdx, [r14+rdx]; unsigned __int16 *
0x180003514  call    ?GetServiceInfo@CDetectionAndSharing@@AEAAJPEBGPEAK1@Z; CDetectionAndSharing::GetServiceInfo(ushort const *,ulong *,ulong *)
0x180003519  test    eax, eax
0x18000351b  js      short loc_180003524
0x18000351d  cmp     [rsp+48h+arg_0], 4
0x180003522  jz      short loc_180003535
0x180003524  movsxd  rcx, dword ptr [r14+r12+10h]
0x180003529  cmp     rcx, [rdi+8]
0x18000352d  jnb     short loc_18000355D
0x18000352f  mov     rax, [rdi]
0x180003532  inc     dword ptr [rax+rcx*8]
0x180003535  inc     ebp
0x180003537  mov     eax, ebp
0x180003539  cmp     rax, [rsi+58h]
0x18000353d  jb      loc_1800034BE
0x180003543  xor     eax, eax
0x180003545  jmp     short loc_18000354C
0x180003547  mov     eax, 8007000Eh
0x18000354c  mov     rbx, [rsp+48h+arg_10]
0x180003551  add     rsp, 20h
0x180003555  pop     r14
0x180003557  pop     r12
0x180003559  pop     rdi
0x18000355a  pop     rsi
0x18000355b  pop     rbp
0x18000355c  retn
0x18000355d  mov     ecx, 80070057h; int
0x180003562  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
