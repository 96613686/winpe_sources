# UlpAllocateRequestQueue

- ea: `0x140095914`
- end: `0x140095c4a`
- name: `UlpAllocateRequestQueue`
- size: `822`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400955b8`

## callees

- `0x14000a350`
- `0x140037060`
- `0x140092c30`
- `0x140095914`
- `0x140095c50`
- `0x140095e80`
- `0x140095ec4`
- `0x14009620c`
- `0x140167c40`
- `0x1401c5fa8`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!ExAllocateCacheAwarePushLock` at `0x140095a88`
- `ntoskrnl!ExAllocateCacheAwarePushLock` at `0x140095a88`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140095a5b`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140095a5b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140095bd0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140095bd0`
- `ntoskrnl!ExAllocatePool3` at `0x14009598f`
- `ntoskrnl!ExAllocatePool3` at `0x14009598f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14017bf12`
- `ntoskrnl!KeInitializeSpinLock` at `0x14017bf12`

## pseudocode

```c
__int64 __fastcall UlpAllocateRequestQueue(__int64 a1, int a2, const UNICODE_STRING *a3, char a4, ULONG_PTR *a5)
{
  ULONG_PTR *v8; // r15
  __int64 *p_Buffer; // rsi
  int v10; // ecx
  unsigned int v11; // ecx
  __int64 Pool3; // rax
  ULONG_PTR v13; // rdi
  __int64 v14; // rcx
  bool v15; // al
  signed __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 CurrentServerSilo; // rax
  __int64 CacheAwarePushLock; // rax
  __int64 v21; // rdx
  int PerNode; // esi
  __int64 v23; // rdx
  int v24; // eax
  unsigned __int16 v26; // bp
  __int64 v27; // r14
  __int64 v28; // rbx
  unsigned int v29; // r8d
  __int16 v30; // [rsp+8Ah] [rbp+12h]

  v30 = HIWORD(a2);
  v8 = a5;
  p_Buffer = (__int64 *)&a3->Buffer;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qllSqq(a1, (unsigned __int16)a2, 1, a1, a2, SBYTE2(a2), *p_Buffer, a4, (char)a5);
  v10 = (unsigned __int16)UlNumberOfLanes + 25;
  *a5 = 0;
  v11 = 16 * v10;
  if ( *p_Buffer )
    v11 += a3->Length + 2;
  Pool3 = ExAllocatePool3(72, v11, 1329687637, UxLowPriorityPool, 1);
  v13 = Pool3;
  if ( !Pool3 )
  {
    PerNode = -1073741670;
    goto LABEL_15;
  }
  *(_DWORD *)(Pool3 + 128) = 1329687637;
  *(_DWORD *)(Pool3 + 276) = a2;
  v14 = Pool3 + 400;
  v15 = (_WORD)a2 == 1 && !v30;
  *(_BYTE *)(v13 + 144) = v15;
  *(_QWORD *)(v13 + 248) = 0;
  *(_QWORD *)(v13 + 16) = 0;
  *(_QWORD *)(v13 + 32) = 0;
  *(_QWORD *)(v13 + 48) = 0;
  v16 = _InterlockedExchangeAdd64(&UxNextRequestQueueId, 1u);
  *(_QWORD *)(v13 + 288) = v14;
  *(_QWORD *)(v13 + 120) = v16 + 1;
  v17 = (unsigned __int16)UlNumberOfLanes;
  v18 = v14 + 8LL * (unsigned __int16)UlNumberOfLanes;
  *(_QWORD *)(v13 + 264) = v18;
  if ( *p_Buffer )
  {
    *(_QWORD *)(v13 + 168) = v18 + 8 * v17;
    *(_WORD *)(v13 + 162) = a3->Length + 2;
    RtlCopyUnicodeString((PUNICODE_STRING)(v13 + 160), a3);
  }
  *(_QWORD *)(v13 + 224) = v13 + 216;
  *(_QWORD *)(v13 + 216) = v13 + 216;
  *(_QWORD *)(v13 + 240) = v13 + 232;
  *(_QWORD *)(v13 + 232) = v13 + 232;
  UlSiqInitialize(v13 + 64, 1);
  *(_DWORD *)v13 = 1;
  CurrentServerSilo = PsGetCurrentServerSilo();
  *(_QWORD *)(v13 + 320) = CurrentServerSilo;
  UxPodReferenceSilo(CurrentServerSilo, 1329687637, 60);
  *(_QWORD *)(v13 + 328) = a1;
  CacheAwarePushLock = ExAllocateCacheAwarePushLock(0);
  *(_QWORD *)(v13 + 280) = CacheAwarePushLock;
  if ( CacheAwarePushLock )
  {
    PerNode = UlAssignSecurity((PSECURITY_DESCRIPTOR *)(v13 + 152));
    if ( PerNode >= 0 )
    {
      PerNode = UlAllocatePerNode(192, v21, 1279355989, *(_QWORD *)(v13 + 288));
      if ( PerNode >= 0 )
      {
        PerNode = UlAllocatePerNode(32, v23, 1430482005, *(_QWORD *)(v13 + 264));
        if ( PerNode >= 0 )
        {
          v26 = 0;
          v27 = MEMORY[0xFFFFF78000000320];
          if ( UlNumberOfLanes )
          {
            do
            {
              UlInitializeAnchor(*(_QWORD *)(*(_QWORD *)(v13 + 264) + 8LL * v26));
              v28 = *(_QWORD *)(*(_QWORD *)(v13 + 288) + 8LL * v26);
              memset((void *)v28, 0, 0xC0u);
              KeInitializeSpinLock((PKSPIN_LOCK)v28);
              v29 = (unsigned __int16)UlNumberOfLanes;
              *(_QWORD *)(v28 + 16) = v28 + 8;
              *(_QWORD *)(v28 + 8) = v28 + 8;
              ++v26;
              *(_QWORD *)(v28 + 32) = v28 + 24;
              *(_QWORD *)(v28 + 24) = v28 + 24;
              *(_QWORD *)(v28 + 96) = v28 + 88;
              *(_QWORD *)(v28 + 88) = v28 + 88;
              *(_QWORD *)(v28 + 56) = v28 + 48;
              *(_QWORD *)(v28 + 48) = v28 + 48;
              *(_QWORD *)(v28 + 72) = v28 + 64;
              *(_QWORD *)(v28 + 64) = v28 + 64;
              *(_DWORD *)(v28 + 104) = 1000;
              *(_DWORD *)(v28 + 108) = 0x3E8 / v29;
              *(_DWORD *)(v28 + 112) = 0x3E8 / v29;
              *(_QWORD *)(v28 + 120) = v27;
            }
            while ( v26 < (unsigned __int16)v29 );
            v8 = a5;
          }
          goto LABEL_15;
        }
      }
    }
  }
  else
  {
    PerNode = -1073741670;
  }
  v24 = _InterlockedDecrement((volatile signed __int32 *)v13);
  if ( UxDebugCheckRefcount && v24 <= -1 )
    UlBugCheckEx(3u, v13, 1u, v24);
  UlFreeRequestQueue((PSECURITY_DESCRIPTOR *)v13);
  v13 = 0;
LABEL_15:
  *v8 = v13;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qD(1032, 55, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v13, PerNode);
  return (unsigned int)PerNode;
}

```

## disassembly

```asm
0x140095914  mov     [rsp+arg_0], rbx
0x140095919  mov     [rsp+arg_10], rbp
0x14009591e  mov     [rsp+arg_8], edx
0x140095922  push    rsi
0x140095923  push    rdi
0x140095924  push    r12
0x140095926  push    r14
0x140095928  push    r15
0x14009592a  sub     rsp, 50h
0x14009592e  mov     rbp, r9
0x140095931  mov     r14, r8
0x140095934  mov     ebx, edx
0x140095936  mov     r12, rcx
0x140095939  mov     r15, [rsp+78h+arg_20]
0x140095941  lea     rsi, [r8+8]
0x140095945  mov     r8d, 1
0x14009594b  test    byte ptr cs:xmmword_1401A2CA0+1, r8b
0x140095952  jnz     loc_140095B45
0x140095958  movzx   ecx, cs:UlNumberOfLanes
0x14009595f  add     ecx, 19h
0x140095962  mov     qword ptr [r15], 0
0x140095969  shl     ecx, 4
0x14009596c  cmp     qword ptr [rsi], 0
0x140095970  jnz     loc_140095B7D
0x140095976  mov     edx, ecx
0x140095978  lea     r9, UxLowPriorityPool
0x14009597f  mov     [rsp+78h+var_58], r8d
0x140095984  mov     ecx, 48h ; 'H'
0x140095989  mov     r8d, 4F416C55h
0x14009598f  call    cs:__imp_ExAllocatePool3
0x140095996  nop     dword ptr [rax+rax+00h]
0x14009599b  mov     rdi, rax
0x14009599e  test    rax, rax
0x1400959a1  jz      loc_140095B8B
0x1400959a7  mov     edx, 1
0x1400959ac  mov     dword ptr [rax+80h], 4F416C55h
0x1400959b6  mov     [rax+114h], ebx
0x1400959bc  lea     rcx, [rax+190h]
0x1400959c3  cmp     dx, bx
0x1400959c6  jz      loc_140095B95
0x1400959cc  xor     al, al
0x1400959ce  mov     [rdi+90h], al
0x1400959d4  mov     rax, rdx
0x1400959d7  mov     qword ptr [rdi+0F8h], 0
0x1400959e2  mov     qword ptr [rdi+10h], 0
0x1400959ea  mov     qword ptr [rdi+20h], 0
0x1400959f2  mov     qword ptr [rdi+30h], 0
0x1400959fa  lock xadd cs:UxNextRequestQueueId, rax
0x140095a03  add     rax, rdx
0x140095a06  mov     [rdi+120h], rcx
0x140095a0d  mov     [rdi+78h], rax
0x140095a11  movzx   eax, cs:UlNumberOfLanes
0x140095a18  lea     rdx, [rcx+rax*8]
0x140095a1c  mov     [rdi+108h], rdx
0x140095a23  cmp     qword ptr [rsi], 0
0x140095a27  jnz     loc_140095BAC
0x140095a2d  lea     rax, [rdi+0D8h]
0x140095a34  mov     ebx, 1
0x140095a39  mov     [rax+8], rax
0x140095a3d  lea     rcx, [rdi+40h]
0x140095a41  mov     [rax], rax
0x140095a44  mov     edx, ebx
0x140095a46  lea     rax, [rdi+0E8h]
0x140095a4d  mov     [rax+8], rax
0x140095a51  mov     [rax], rax
0x140095a54  call    UlSiqInitialize
0x140095a59  mov     [rdi], ebx
0x140095a5b  call    cs:__imp_PsGetCurrentServerSilo
0x140095a62  nop     dword ptr [rax+rax+00h]
0x140095a67  mov     edx, 4F416C55h
0x140095a6c  lea     r8d, [rbx+3Bh]
0x140095a70  mov     rcx, rax
0x140095a73  mov     [rdi+140h], rax
0x140095a7a  call    UxPodReferenceSilo
0x140095a7f  xor     ecx, ecx
0x140095a81  mov     [rdi+148h], r12
0x140095a88  call    cs:__imp_ExAllocateCacheAwarePushLock
0x140095a8f  nop     dword ptr [rax+rax+00h]
0x140095a94  mov     [rdi+118h], rax
0x140095a9b  test    rax, rax
0x140095a9e  jz      loc_140095B25
0x140095aa4  lea     rcx, [rdi+98h]; NewDescriptor
0x140095aab  mov     rdx, rbp
0x140095aae  call    UlAssignSecurity
0x140095ab3  mov     esi, eax
0x140095ab5  test    eax, eax
0x140095ab7  js      short loc_140095ADE
0x140095ab9  mov     r9, [rdi+120h]
0x140095ac0  mov     r12d, 0C0h
0x140095ac6  mov     ecx, r12d
0x140095ac9  mov     r8d, 4C416C55h
0x140095acf  call    UlAllocatePerNode
0x140095ad4  mov     esi, eax
0x140095ad6  test    eax, eax
0x140095ad8  jns     loc_140095BE1
0x140095ade  or      eax, 0FFFFFFFFh
0x140095ae1  lock xadd [rdi], eax
0x140095ae5  dec     eax
0x140095ae7  cmp     cs:UxDebugCheckRefcount, 0
0x140095aee  jnz     short loc_140095B2C
0x140095af0  mov     rcx, rdi; P
0x140095af3  call    UlFreeRequestQueue
0x140095af8  xor     edi, edi
0x140095afa  mov     [r15], rdi
0x140095afd  test    byte ptr cs:xmmword_1401A2CA0+1, bl
0x140095b03  jnz     loc_140095C28
0x140095b09  lea     r11, [rsp+78h+var_28]
0x140095b0e  mov     eax, esi
0x140095b10  mov     rbx, [r11+30h]
0x140095b14  mov     rbp, [r11+40h]
0x140095b18  mov     rsp, r11
0x140095b1b  pop     r15
0x140095b1d  pop     r14
0x140095b1f  pop     r12
0x140095b21  pop     rdi
0x140095b22  pop     rsi
0x140095b23  retn
0x140095b25  mov     esi, 0C000009Ah
0x140095b2a  jmp     short loc_140095ADE
0x140095b2c  cmp     eax, 0FFFFFFFFh
0x140095b2f  jg      short loc_140095AF0
0x140095b31  movsxd  r9, eax; BugCheckParameter4
0x140095b34  mov     r8, rbx; BugCheckParameter3
0x140095b37  mov     rdx, rdi; BugCheckParameter2
0x140095b3a  mov     ecx, 3; BugCheckParameter1
0x140095b3f  call    UlBugCheckEx
0x140095b45  mov     rax, [rsi]
0x140095b48  mov     r9d, ebx
0x140095b4b  mov     [rsp+78h+var_38], r15
0x140095b50  shr     r9d, 10h
0x140095b54  mov     [rsp+78h+var_40], rbp
0x140095b59  mov     [rsp+78h+var_48], rax
0x140095b5e  mov     [rsp+78h+var_50], r9d
0x140095b63  mov     r9, r12
0x140095b66  movzx   edx, bx
0x140095b69  mov     [rsp+78h+var_58], edx
0x140095b6d  call    WPP_SF_qllSqq
0x140095b72  mov     r8d, 1
0x140095b78  jmp     loc_140095958
0x140095b7d  movzx   eax, word ptr [r14]
0x140095b81  add     ecx, 2
0x140095b84  add     ecx, eax
0x140095b86  jmp     loc_140095976
0x140095b8b  mov     esi, 0C000009Ah
0x140095b90  jmp     loc_14017BEDA
0x140095b95  xor     eax, eax
0x140095b97  cmp     ax, word ptr [rsp+78h+arg_8+2]
0x140095b9f  jnz     loc_1400959CC
0x140095ba5  mov     al, dl
0x140095ba7  jmp     loc_1400959CE
0x140095bac  lea     rax, [rdx+rax*8]
0x140095bb0  mov     rdx, r14; SourceString
0x140095bb3  mov     [rdi+0A8h], rax
0x140095bba  lea     rcx, [rdi+0A0h]; DestinationString
0x140095bc1  movzx   eax, word ptr [r14]
0x140095bc5  add     ax, 2
0x140095bc9  mov     [rdi+0A2h], ax
0x140095bd0  call    cs:__imp_RtlCopyUnicodeString
0x140095bd7  nop     dword ptr [rax+rax+00h]
0x140095bdc  jmp     loc_140095A2D
0x140095be1  mov     r9, [rdi+108h]
0x140095be8  mov     ecx, 20h ; ' '
0x140095bed  mov     r8d, 55436C55h
0x140095bf3  call    UlAllocatePerNode
0x140095bf8  mov     esi, eax
0x140095bfa  test    eax, eax
0x140095bfc  js      loc_140095ADE
0x140095c02  mov     r14, 0FFFFF78000000320h
0x140095c0c  xor     ebp, ebp
0x140095c0e  xor     eax, eax
0x140095c10  mov     r14, [r14]
0x140095c13  cmp     ax, cs:UlNumberOfLanes
0x140095c1a  jnb     loc_140095AFA
0x140095c20  mov     r15, rbx
0x140095c23  jmp     loc_14017BEE4
0x140095c28  mov     edx, 37h ; '7'
0x140095c2d  mov     [rsp+78h+var_58], esi
0x140095c31  mov     ecx, 408h
0x140095c36  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140095c3d  mov     r9, rdi
0x140095c40  call    WPP_SF_qD
0x140095c45  jmp     loc_140095B09
0x14017bed2  mov     r15, [rsp+78h+arg_20]
0x14017beda  mov     ebx, 1
0x14017bedf  jmp     loc_140095AFA
0x14017bee4  mov     rcx, [rdi+108h]
0x14017beeb  movzx   ebx, bp
0x14017beee  mov     rcx, [rcx+rbx*8]
0x14017bef2  call    UlInitializeAnchor
0x14017bef7  mov     rax, [rdi+120h]
0x14017befe  mov     r8, r12; Size
0x14017bf01  xor     edx, edx; Val
0x14017bf03  mov     rbx, [rax+rbx*8]
0x14017bf07  mov     rcx, rbx; void *
0x14017bf0a  call    memset
0x14017bf0f  mov     rcx, rbx; SpinLock
0x14017bf12  call    cs:__imp_KeInitializeSpinLock
0x14017bf19  nop     dword ptr [rax+rax+00h]
0x14017bf1e  movzx   r8d, cs:UlNumberOfLanes
0x14017bf26  lea     rax, [rbx+8]
0x14017bf2a  mov     [rbx+10h], rax
0x14017bf2e  xor     edx, edx
0x14017bf30  mov     [rax], rax
0x14017bf33  add     bp, r15w
0x14017bf37  lea     rax, [rbx+18h]
0x14017bf3b  mov     [rbx+20h], rax
0x14017bf3f  mov     [rax], rax
0x14017bf42  lea     rax, [rbx+58h]
0x14017bf46  mov     [rbx+60h], rax
0x14017bf4a  mov     [rax], rax
0x14017bf4d  lea     rax, [rbx+30h]
0x14017bf51  mov     [rbx+38h], rax
0x14017bf55  mov     [rax], rax
0x14017bf58  lea     rax, [rbx+40h]
0x14017bf5c  mov     [rbx+48h], rax
0x14017bf60  mov     [rax], rax
0x14017bf63  mov     eax, 3E8h
0x14017bf68  div     r8d
0x14017bf6b  mov     dword ptr [rbx+68h], 3E8h
0x14017bf72  mov     [rbx+6Ch], eax
0x14017bf75  mov     [rbx+70h], eax
0x14017bf78  mov     [rbx+78h], r14
0x14017bf7c  cmp     bp, r8w
0x14017bf80  jb      loc_14017BEE4
0x14017bf86  jmp     loc_14017BED2
```
