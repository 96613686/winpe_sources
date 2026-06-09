# SpFreeCredentialsHandle(unsigned __int64)

- ea: `0x1800032c0`
- end: `0x1800034ee`
- name: `?SpFreeCredentialsHandle@@YAJ_K@Z`
- size: `558`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800032c0`
- `0x180004230`
- `0x18000ff54`
- `0x18000ffa4`
- `0x18001ecee`
- `0x18001ed20`
- `0x180020010`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800033aa`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800033aa`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180003370`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180003370`
- `ntdll!RtlAcquireResourceExclusive` at `0x180003361`
- `ntdll!RtlAcquireResourceExclusive` at `0x180003361`
- `ntdll!RtlReleaseResource` at `0x1800033c8`
- `ntdll!RtlReleaseResource` at `0x18000345d`
- `ntdll!RtlReleaseResource` at `0x180003489`
- `ntdll!RtlReleaseResource` at `0x1800033c8`
- `ntdll!RtlReleaseResource` at `0x18000345d`
- `ntdll!RtlReleaseResource` at `0x180003489`

## pseudocode

```c
__int64 __fastcall SpFreeCredentialsHandle(struct basessp::_WST_CREDENTIAL *a1)
{
  basessp::BaseSSP *v2; // rbx
  __int64 v3; // rax
  volatile signed __int32 *v4; // rax
  int v5; // r8d
  PVOID *v6; // rcx
  unsigned int v7; // ebx
  __int128 v9; // [rsp+30h] [rbp-E8h] BYREF
  __int64 v10; // [rsp+40h] [rbp-D8h]
  struct basessp::_WST_CREDENTIAL *Buffer[20]; // [rsp+50h] [rbp-C8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_e6056710a2583024a4e9a9c13fd9c851_Traceguids, a1);
  v2 = WSTGlobalBaseSSP;
  memset_0(Buffer, 0, 0x98u);
  v10 = 0;
  v3 = *((_QWORD *)v2 + 30);
  v9 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(__int128 *))(v3 + 192))(&v9) )
  {
    Buffer[0] = a1;
    RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)v2 + 112), 1u);
    v4 = (volatile signed __int32 *)RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v2 + 8), Buffer);
    if ( v4 )
    {
      v5 = 1;
      if ( HIDWORD(v9) )
        v5 = HIDWORD(v9);
      _InterlockedAdd(v4 + 2, -v5);
      if ( *((int *)v4 + 2) <= 0 && RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v2 + 8), Buffer) )
      {
        *((_DWORD *)Buffer[0] + 3) = 0;
        RtlReleaseResource((PRTL_RESOURCE)((char *)v2 + 112));
        basessp::BaseSSP::WSTDereferenceCredential(v2, Buffer[0]);
      }
      else
      {
        RtlReleaseResource((PRTL_RESOURCE)((char *)v2 + 112));
      }
      v6 = (PVOID *)WPP_GLOBAL_Control;
      v7 = 0;
    }
    else
    {
      RtlReleaseResource((PRTL_RESOURCE)((char *)v2 + 112));
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_e2b939a1f5e739f8a467c1749fa620e3_Traceguids, a1);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      v7 = -1073741816;
    }
  }
  else
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v7 = -1073741595;
  }
  if ( v6 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v6 + 28) & 0x10) != 0 )
    {
      WPP_SF_q(v6[2], 14, WPP_e6056710a2583024a4e9a9c13fd9c851_Traceguids, a1);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
      WPP_SF_Dq(v6[2], 15, WPP_e6056710a2583024a4e9a9c13fd9c851_Traceguids, v7, a1);
  }
  return v7;
}

```

## disassembly

```asm
0x1800032c0  push    rbx
0x1800032c2  push    rdi
0x1800032c3  push    r14
0x1800032c5  sub     rsp, 100h
0x1800032cc  mov     rax, cs:__security_cookie
0x1800032d3  xor     rax, rsp
0x1800032d6  mov     [rsp+118h+var_28], rax
0x1800032de  mov     rdi, rcx
0x1800032e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032e8  lea     r14, WPP_GLOBAL_Control
0x1800032ef  cmp     rcx, r14
0x1800032f2  jz      short loc_1800032FE
0x1800032f4  test    byte ptr [rcx+1Ch], 8
0x1800032f8  jnz     loc_180003468
0x1800032fe  mov     rbx, cs:?WSTGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * WSTGlobalBaseSSP
0x180003305  lea     rcx, [rsp+118h+Buffer]; void *
0x18000330a  xor     edx, edx; Val
0x18000330c  mov     r8d, 98h; Size
0x180003312  call    memset_0
0x180003317  xor     eax, eax
0x180003319  lea     rcx, [rsp+118h+var_E8]
0x18000331e  mov     [rsp+118h+var_D8], rax
0x180003323  xorps   xmm0, xmm0
0x180003326  mov     rax, [rbx+0F0h]
0x18000332d  movups  [rsp+118h+var_E8], xmm0
0x180003332  mov     rax, [rax+0C0h]
0x180003339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000333e  test    al, al
0x180003340  jz      loc_18000344B
0x180003346  mov     [rsp+118h+arg_8], rbp
0x18000334e  lea     rcx, [rbx+70h]; Resource
0x180003352  mov     dl, 1; Wait
0x180003354  mov     [rsp+118h+arg_10], rsi
0x18000335c  mov     [rsp+118h+Buffer], rdi
0x180003361  call    cs:__imp_RtlAcquireResourceExclusive
0x180003367  lea     rdx, [rsp+118h+Buffer]; Buffer
0x18000336c  lea     rcx, [rbx+8]; Table
0x180003370  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180003376  test    rax, rax
0x180003379  jz      loc_180003485
0x18000337f  mov     edx, dword ptr [rsp+118h+var_E8+0Ch]
0x180003383  mov     r8d, 1
0x180003389  test    edx, edx
0x18000338b  cmovnz  r8d, edx
0x18000338f  neg     r8d
0x180003392  lock add [rax+8], r8d
0x180003397  cmp     dword ptr [rax+8], 0
0x18000339b  jg      loc_180003459
0x1800033a1  lea     rdx, [rsp+118h+Buffer]; Buffer
0x1800033a6  lea     rcx, [rbx+8]; Table
0x1800033aa  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800033b0  test    al, al
0x1800033b2  jz      loc_180003459
0x1800033b8  mov     rax, [rsp+118h+Buffer]
0x1800033bd  lea     rcx, [rbx+70h]; Resource
0x1800033c1  mov     dword ptr [rax+0Ch], 0
0x1800033c8  call    cs:__imp_RtlReleaseResource
0x1800033ce  mov     rdx, [rsp+118h+Buffer]; struct basessp::_WST_CREDENTIAL *
0x1800033d3  mov     rcx, rbx; this
0x1800033d6  call    ?WSTDereferenceCredential@BaseSSP@basessp@@QEAAXPEAU_WST_CREDENTIAL@2@@Z; basessp::BaseSSP::WSTDereferenceCredential(basessp::_WST_CREDENTIAL *)
0x1800033db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033e2  xor     ebx, ebx
0x1800033e4  mov     rbp, [rsp+118h+arg_8]
0x1800033ec  mov     rsi, [rsp+118h+arg_10]
0x1800033f4  cmp     rcx, r14
0x1800033f7  jnz     short loc_180003417
0x1800033f9  mov     eax, ebx
0x1800033fb  mov     rcx, [rsp+118h+var_28]
0x180003403  xor     rcx, rsp; StackCookie
0x180003406  call    __security_check_cookie
0x18000340b  add     rsp, 100h
0x180003412  pop     r14
0x180003414  pop     rdi
0x180003415  pop     rbx
0x180003416  retn
0x180003417  test    byte ptr [rcx+1Ch], 10h
0x18000341b  jnz     loc_1800034CA
0x180003421  cmp     rcx, r14
0x180003424  jz      short loc_1800033F9
0x180003426  test    byte ptr [rcx+1Ch], 8
0x18000342a  jz      short loc_1800033F9
0x18000342c  mov     rcx, [rcx+10h]
0x180003430  lea     r8, WPP_e6056710a2583024a4e9a9c13fd9c851_Traceguids
0x180003437  mov     edx, 0Fh
0x18000343c  mov     [rsp+118h+var_F8], rdi
0x180003441  mov     r9d, ebx
0x180003444  call    WPP_SF_Dq
0x180003449  jmp     short loc_1800033F9
0x18000344b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003452  mov     ebx, 0C00000E5h
0x180003457  jmp     short loc_1800033F4
0x180003459  lea     rcx, [rbx+70h]; Resource
0x18000345d  call    cs:__imp_RtlReleaseResource
0x180003463  jmp     loc_1800033DB
0x180003468  mov     rcx, [rcx+10h]
0x18000346c  lea     r8, WPP_e6056710a2583024a4e9a9c13fd9c851_Traceguids
0x180003473  mov     edx, 0Dh
0x180003478  mov     r9, rdi
0x18000347b  call    WPP_SF_q
0x180003480  jmp     loc_1800032FE
0x180003485  lea     rcx, [rbx+70h]; Resource
0x180003489  call    cs:__imp_RtlReleaseResource
0x18000348f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003496  cmp     rcx, r14
0x180003499  jz      short loc_1800034C0
0x18000349b  test    byte ptr [rcx+1Ch], 10h
0x18000349f  jz      short loc_1800034C0
0x1800034a1  mov     rcx, [rcx+10h]
0x1800034a5  lea     r8, WPP_e2b939a1f5e739f8a467c1749fa620e3_Traceguids
0x1800034ac  mov     edx, 0Ah
0x1800034b1  mov     r9, rdi
0x1800034b4  call    WPP_SF_q
0x1800034b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034c0  mov     ebx, 0C0000008h
0x1800034c5  jmp     loc_1800033E4
0x1800034ca  mov     rcx, [rcx+10h]
0x1800034ce  lea     r8, WPP_e6056710a2583024a4e9a9c13fd9c851_Traceguids
0x1800034d5  mov     edx, 0Eh
0x1800034da  mov     r9, rdi
0x1800034dd  call    WPP_SF_q
0x1800034e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034e9  jmp     loc_180003421
```
