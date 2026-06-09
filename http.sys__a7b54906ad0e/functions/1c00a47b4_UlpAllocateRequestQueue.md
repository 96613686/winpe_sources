# UlpAllocateRequestQueue

- ea: `0x1c00a47b4`
- end: `0x1c00a4a2b`
- name: `UlpAllocateRequestQueue`
- size: `631`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1c00a2db0`

## callees

- `0x1c00020e8`
- `0x1c0002130`
- `0x1c000217c`
- `0x1c001b900`
- `0x1c008f570`
- `0x1c009089c`
- `0x1c00a47b4`
- `0x1c00a4db4`
- `0x1c00a4ea4`
- `0x1c00a93f4`

## import_xrefs

- `ntoskrnl!ExAllocateCacheAwarePushLock` at `0x1c00a48fd`
- `ntoskrnl!ExAllocateCacheAwarePushLock` at `0x1c00a48fd`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1c00a48cc`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1c00a48cc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1c00ded28`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1c00ded28`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00a481f`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00a481f`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c00a498f`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c00a498f`

## pseudocode

```c
__int64 __fastcall UlpAllocateRequestQueue(__int64 a1, unsigned int a2, unsigned __int16 *a3, char a4, _QWORD *a5)
{
  int v7; // eax
  unsigned __int16 v8; // si
  unsigned int v9; // ecx
  unsigned int v10; // r12d
  char *PoolWithTagPriority; // rax
  char *v12; // rdi
  char *v13; // r13
  char v14; // al
  __int64 CurrentServerSilo; // rax
  __int64 CacheAwarePushLock; // rax
  int PerNode; // ebp
  __int64 v18; // r14
  __int64 v19; // rbx
  unsigned int v20; // r8d
  __int16 v23; // [rsp+8Ah] [rbp+12h]

  v23 = HIWORD(a2);
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_qllSqq(a1, HIWORD(a2), a1, (unsigned __int16)a2, SBYTE2(a2), *((_QWORD *)a3 + 1), a4, (char)a5);
  v7 = (unsigned __int16)UlNumberOfLanes;
  v8 = 0;
  *a5 = 0;
  v9 = 8 * v7 + 336;
  if ( *((_QWORD *)a3 + 1) )
    v9 = *a3 + 8 * v7 + 338;
  v10 = v9;
  PoolWithTagPriority = (char *)ExAllocatePoolWithTagPriority((POOL_TYPE)516, v9, 0x4F416C55u, LowPoolPriority);
  v12 = PoolWithTagPriority;
  if ( !PoolWithTagPriority )
  {
    PerNode = -1073741670;
    goto LABEL_15;
  }
  v13 = PoolWithTagPriority + 336;
  memset(PoolWithTagPriority, 0, v10);
  *((_DWORD *)v12 + 30) = 1329687637;
  *((_DWORD *)v12 + 69) = a2;
  if ( (_WORD)a2 != 1 || (v14 = 1, v23) )
    v14 = 0;
  *((_QWORD *)v12 + 2) = 0;
  *((_QWORD *)v12 + 4) = 0;
  *((_QWORD *)v12 + 6) = 0;
  *((_QWORD *)v12 + 36) = v13;
  v12[136] = v14;
  *((_QWORD *)v12 + 28) = 0;
  if ( *((_QWORD *)a3 + 1) )
  {
    *((_QWORD *)v12 + 20) = &v13[8 * (unsigned __int16)UlNumberOfLanes];
    *((_WORD *)v12 + 77) = *a3 + 2;
    RtlCopyUnicodeString((PUNICODE_STRING)(v12 + 152), (PCUNICODE_STRING)a3);
  }
  *((_QWORD *)v12 + 27) = v12 + 208;
  *((_QWORD *)v12 + 26) = v12 + 208;
  UlSiqInitialize(v12 + 64, 1);
  UlInitializeAnchor(v12 + 240);
  *(_DWORD *)v12 = 1;
  CurrentServerSilo = PsGetCurrentServerSilo();
  *((_QWORD *)v12 + 40) = CurrentServerSilo;
  UxPodReferenceSilo(CurrentServerSilo, 1329687637);
  *((_QWORD *)v12 + 41) = a1;
  CacheAwarePushLock = ExAllocateCacheAwarePushLock(0);
  *((_QWORD *)v12 + 35) = CacheAwarePushLock;
  if ( !CacheAwarePushLock )
  {
    PerNode = -1073741670;
LABEL_21:
    _InterlockedDecrement((volatile signed __int32 *)v12);
    UlFreeRequestQueue((PSECURITY_DESCRIPTOR *)v12);
    v12 = 0;
    goto LABEL_15;
  }
  PerNode = UlAssignSecurity((PSECURITY_DESCRIPTOR *)v12 + 18);
  if ( PerNode < 0 )
    goto LABEL_21;
  PerNode = UlAllocatePerNode(0xC0u);
  if ( PerNode < 0 )
    goto LABEL_21;
  v18 = MEMORY[0xFFFFF78000000320];
  if ( UlNumberOfLanes )
  {
    do
    {
      v19 = *(_QWORD *)(*((_QWORD *)v12 + 36) + 8LL * v8);
      memset((void *)v19, 0, 0xC0u);
      KeInitializeSpinLock((PKSPIN_LOCK)v19);
      v20 = (unsigned __int16)UlNumberOfLanes;
      *(_QWORD *)(v19 + 16) = v19 + 8;
      *(_QWORD *)(v19 + 8) = v19 + 8;
      ++v8;
      *(_QWORD *)(v19 + 112) = v18;
      *(_QWORD *)(v19 + 32) = v19 + 24;
      *(_QWORD *)(v19 + 24) = v19 + 24;
      *(_QWORD *)(v19 + 88) = v19 + 80;
      *(_QWORD *)(v19 + 80) = v19 + 80;
      *(_QWORD *)(v19 + 48) = v19 + 40;
      *(_QWORD *)(v19 + 40) = v19 + 40;
      *(_QWORD *)(v19 + 64) = v19 + 56;
      *(_QWORD *)(v19 + 56) = v19 + 56;
      *(_DWORD *)(v19 + 96) = 1000;
      *(_DWORD *)(v19 + 100) = 0x3E8 / v20;
      *(_DWORD *)(v19 + 104) = 0x3E8 / v20;
    }
    while ( v8 < (unsigned __int16)v20 );
  }
LABEL_15:
  *a5 = v12;
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_qD(54, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, v12, (unsigned int)PerNode);
  return (unsigned int)PerNode;
}

```

## disassembly

```asm
0x1c00a47b4  mov     [rsp+arg_10], rbx
0x1c00a47b9  mov     [rsp+arg_8], edx
0x1c00a47bd  mov     [rsp+arg_0], rcx
0x1c00a47c2  push    rbp
0x1c00a47c3  push    rsi
0x1c00a47c4  push    rdi
0x1c00a47c5  push    r12
0x1c00a47c7  push    r13
0x1c00a47c9  push    r14
0x1c00a47cb  push    r15
0x1c00a47cd  sub     rsp, 40h
0x1c00a47d1  mov     rbp, r9
0x1c00a47d4  mov     r14, r8
0x1c00a47d7  mov     ebx, edx
0x1c00a47d9  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a47df  mov     r15, [rsp+78h+arg_20]
0x1c00a47e7  test    al, al
0x1c00a47e9  js      loc_1C00DECAA
0x1c00a47ef  movzx   eax, cs:UlNumberOfLanes
0x1c00a47f6  xor     esi, esi
0x1c00a47f8  mov     [r15], rsi
0x1c00a47fb  lea     ecx, ds:150h[rax*8]
0x1c00a4802  cmp     [r14+8], rsi
0x1c00a4806  jnz     loc_1C00DECD6
0x1c00a480c  mov     r12d, ecx
0x1c00a480f  xor     r9d, r9d; Priority
0x1c00a4812  mov     edx, ecx; NumberOfBytes
0x1c00a4814  mov     r8d, 4F416C55h; Tag
0x1c00a481a  mov     ecx, 204h; PoolType
0x1c00a481f  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c00a4826  nop     dword ptr [rax+rax+00h]
0x1c00a482b  mov     rdi, rax
0x1c00a482e  test    rax, rax
0x1c00a4831  jz      loc_1C00DECE4
0x1c00a4837  mov     r8d, r12d; Size
0x1c00a483a  lea     r13, [rax+150h]
0x1c00a4841  xor     edx, edx; Val
0x1c00a4843  mov     rcx, rax; void *
0x1c00a4846  call    memset
0x1c00a484b  mov     r12d, 1
0x1c00a4851  mov     dword ptr [rdi+78h], 4F416C55h
0x1c00a4858  mov     [rdi+114h], ebx
0x1c00a485e  cmp     r12w, bx
0x1c00a4862  jnz     loc_1C00DECEE
0x1c00a4868  mov     al, r12b
0x1c00a486b  cmp     si, word ptr [rsp+78h+arg_8+2]
0x1c00a4873  jnz     loc_1C00DECEE
0x1c00a4879  mov     [rdi+10h], rsi
0x1c00a487d  mov     [rdi+20h], rsi
0x1c00a4881  mov     [rdi+30h], rsi
0x1c00a4885  mov     [rdi+120h], r13
0x1c00a488c  mov     [rdi+88h], al
0x1c00a4892  mov     [rdi+0E0h], rsi
0x1c00a4899  cmp     [r14+8], rsi
0x1c00a489d  jnz     loc_1C00DECF6
0x1c00a48a3  lea     rax, [rdi+0D0h]
0x1c00a48aa  mov     edx, r12d
0x1c00a48ad  lea     rcx, [rdi+40h]
0x1c00a48b1  mov     [rax+8], rax
0x1c00a48b5  mov     [rax], rax
0x1c00a48b8  call    UlSiqInitialize
0x1c00a48bd  lea     rcx, [rdi+0F0h]
0x1c00a48c4  call    UlInitializeAnchor
0x1c00a48c9  mov     [rdi], r12d
0x1c00a48cc  call    cs:__imp_PsGetCurrentServerSilo
0x1c00a48d3  nop     dword ptr [rax+rax+00h]
0x1c00a48d8  mov     rcx, rax
0x1c00a48db  mov     [rdi+140h], rax
0x1c00a48e2  mov     edx, 4F416C55h
0x1c00a48e7  call    UxPodReferenceSilo
0x1c00a48ec  mov     rax, [rsp+78h+arg_0]
0x1c00a48f4  xor     ecx, ecx
0x1c00a48f6  mov     [rdi+148h], rax
0x1c00a48fd  call    cs:__imp_ExAllocateCacheAwarePushLock
0x1c00a4904  nop     dword ptr [rax+rax+00h]
0x1c00a4909  mov     [rdi+118h], rax
0x1c00a4910  test    rax, rax
0x1c00a4913  jz      loc_1C00DED3A
0x1c00a4919  lea     rcx, [rdi+90h]; NewDescriptor
0x1c00a4920  mov     rdx, rbp
0x1c00a4923  call    UlAssignSecurity
0x1c00a4928  mov     ebp, eax
0x1c00a492a  test    eax, eax
0x1c00a492c  js      loc_1C00DED3F
0x1c00a4932  mov     r9, [rdi+120h]
0x1c00a4939  mov     r13d, 0C0h
0x1c00a493f  mov     ecx, r13d; NumberOfBytes
0x1c00a4942  mov     r8d, 4C416C55h
0x1c00a4948  call    UlAllocatePerNode
0x1c00a494d  mov     ebp, eax
0x1c00a494f  test    eax, eax
0x1c00a4951  js      loc_1C00DED3F
0x1c00a4957  mov     r14, 0FFFFF78000000320h
0x1c00a4961  mov     r14, [r14]
0x1c00a4964  cmp     si, cs:UlNumberOfLanes
0x1c00a496b  jnb     loc_1C00A49FF
0x1c00a4971  mov     rax, [rdi+120h]
0x1c00a4978  mov     r8, r13; Size
0x1c00a497b  movzx   ecx, si
0x1c00a497e  xor     edx, edx; Val
0x1c00a4980  mov     rbx, [rax+rcx*8]
0x1c00a4984  mov     rcx, rbx; void *
0x1c00a4987  call    memset
0x1c00a498c  mov     rcx, rbx; SpinLock
0x1c00a498f  call    cs:__imp_KeInitializeSpinLock
0x1c00a4996  nop     dword ptr [rax+rax+00h]
0x1c00a499b  movzx   r8d, cs:UlNumberOfLanes
0x1c00a49a3  lea     rax, [rbx+8]
0x1c00a49a7  mov     [rax+8], rax
0x1c00a49ab  xor     edx, edx
0x1c00a49ad  mov     [rax], rax
0x1c00a49b0  add     si, r12w
0x1c00a49b4  lea     rax, [rbx+18h]
0x1c00a49b8  mov     [rbx+70h], r14
0x1c00a49bc  mov     [rax+8], rax
0x1c00a49c0  mov     [rax], rax
0x1c00a49c3  lea     rax, [rbx+50h]
0x1c00a49c7  mov     [rax+8], rax
0x1c00a49cb  mov     [rax], rax
0x1c00a49ce  lea     rax, [rbx+28h]
0x1c00a49d2  mov     [rax+8], rax
0x1c00a49d6  mov     [rax], rax
0x1c00a49d9  lea     rax, [rbx+38h]
0x1c00a49dd  mov     [rax+8], rax
0x1c00a49e1  mov     [rax], rax
0x1c00a49e4  mov     eax, 3E8h
0x1c00a49e9  mov     [rbx+60h], eax
0x1c00a49ec  div     r8d
0x1c00a49ef  mov     [rbx+64h], eax
0x1c00a49f2  mov     [rbx+68h], eax
0x1c00a49f5  cmp     si, r8w
0x1c00a49f9  jb      loc_1C00A4971
0x1c00a49ff  mov     [r15], rdi
0x1c00a4a02  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a4a08  test    al, al
0x1c00a4a0a  js      loc_1C00DED52
0x1c00a4a10  mov     rbx, [rsp+78h+arg_10]
0x1c00a4a18  mov     eax, ebp
0x1c00a4a1a  add     rsp, 40h
0x1c00a4a1e  pop     r15
0x1c00a4a20  pop     r14
0x1c00a4a22  pop     r13
0x1c00a4a24  pop     r12
0x1c00a4a26  pop     rdi
0x1c00a4a27  pop     rsi
0x1c00a4a28  pop     rbp
0x1c00a4a29  retn
0x1c00decaa  mov     rax, [r8+8]
0x1c00decae  mov     r8, rcx
0x1c00decb1  mov     [rsp+78h+var_40], r15
0x1c00decb6  mov     [rsp+78h+var_48], rbp
0x1c00decbb  shr     edx, 10h
0x1c00decbe  mov     [rsp+78h+var_50], rax
0x1c00decc3  movzx   r9d, bx
0x1c00decc7  mov     [rsp+78h+var_58], edx
0x1c00deccb  call    WPP_SF_qllSqq
0x1c00decd0  nop
0x1c00decd1  jmp     loc_1C00A47EF
0x1c00decd6  movzx   eax, word ptr [r14]
0x1c00decda  add     ecx, 2
0x1c00decdd  add     ecx, eax
0x1c00decdf  jmp     loc_1C00A480C
0x1c00dece4  mov     ebp, 0C000009Ah
0x1c00dece9  jmp     loc_1C00A49FF
0x1c00decee  mov     al, sil
0x1c00decf1  jmp     loc_1C00A4879
0x1c00decf6  movzx   eax, cs:UlNumberOfLanes
0x1c00decfd  mov     rdx, r14; SourceString
0x1c00ded00  lea     rcx, ds:0[rax*8]
0x1c00ded08  add     rcx, r13
0x1c00ded0b  mov     [rdi+0A0h], rcx
0x1c00ded12  lea     rcx, [rdi+98h]; DestinationString
0x1c00ded19  movzx   eax, word ptr [r14]
0x1c00ded1d  add     ax, 2
0x1c00ded21  mov     [rdi+9Ah], ax
0x1c00ded28  call    cs:__imp_RtlCopyUnicodeString
0x1c00ded2f  nop     dword ptr [rax+rax+00h]
0x1c00ded34  nop
0x1c00ded35  jmp     loc_1C00A48A3
0x1c00ded3a  mov     ebp, 0C000009Ah
0x1c00ded3f  lock dec dword ptr [rdi]
0x1c00ded42  mov     rcx, rdi; P
0x1c00ded45  call    UlFreeRequestQueue
0x1c00ded4a  mov     rdi, rsi
0x1c00ded4d  jmp     loc_1C00A49FF
0x1c00ded52  mov     ecx, 36h ; '6'
0x1c00ded57  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00ded5e  mov     r9d, ebp
0x1c00ded61  mov     r8, rdi
0x1c00ded64  call    WPP_SF_qD
0x1c00ded69  nop
0x1c00ded6a  jmp     loc_1C00A4A10
```
