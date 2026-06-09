# UlpAllocateRequestQueue

- ea: `0x140095934`
- end: `0x140095c6a`
- name: `UlpAllocateRequestQueue`
- size: `822`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400955d8`

## callees

- `0x14000a350`
- `0x140037080`
- `0x140092c50`
- `0x140095934`
- `0x140095c70`
- `0x140095ea0`
- `0x140095ee4`
- `0x14009622c`
- `0x140167b40`
- `0x1401c5fa8`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!ExAllocateCacheAwarePushLock` at `0x140095aa8`
- `ntoskrnl!ExAllocateCacheAwarePushLock` at `0x140095aa8`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140095a7b`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140095a7b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140095bf0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140095bf0`
- `ntoskrnl!ExAllocatePool3` at `0x1400959af`
- `ntoskrnl!ExAllocatePool3` at `0x1400959af`
- `ntoskrnl!KeInitializeSpinLock` at `0x14017be12`
- `ntoskrnl!KeInitializeSpinLock` at `0x14017be12`

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
0x140095934  mov     [rsp+arg_0], rbx
0x140095939  mov     [rsp+arg_10], rbp
0x14009593e  mov     [rsp+arg_8], edx
0x140095942  push    rsi
0x140095943  push    rdi
0x140095944  push    r12
0x140095946  push    r14
0x140095948  push    r15
0x14009594a  sub     rsp, 50h
0x14009594e  mov     rbp, r9
0x140095951  mov     r14, r8
0x140095954  mov     ebx, edx
0x140095956  mov     r12, rcx
0x140095959  mov     r15, [rsp+78h+arg_20]
0x140095961  lea     rsi, [r8+8]
0x140095965  mov     r8d, 1
0x14009596b  test    byte ptr cs:xmmword_1401A2CA0+1, r8b
0x140095972  jnz     loc_140095B65
0x140095978  movzx   ecx, cs:UlNumberOfLanes
0x14009597f  add     ecx, 19h
0x140095982  mov     qword ptr [r15], 0
0x140095989  shl     ecx, 4
0x14009598c  cmp     qword ptr [rsi], 0
0x140095990  jnz     loc_140095B9D
0x140095996  mov     edx, ecx
0x140095998  lea     r9, UxLowPriorityPool
0x14009599f  mov     [rsp+78h+var_58], r8d
0x1400959a4  mov     ecx, 48h ; 'H'
0x1400959a9  mov     r8d, 4F416C55h
0x1400959af  call    cs:__imp_ExAllocatePool3
0x1400959b6  nop     dword ptr [rax+rax+00h]
0x1400959bb  mov     rdi, rax
0x1400959be  test    rax, rax
0x1400959c1  jz      loc_140095BAB
0x1400959c7  mov     edx, 1
0x1400959cc  mov     dword ptr [rax+80h], 4F416C55h
0x1400959d6  mov     [rax+114h], ebx
0x1400959dc  lea     rcx, [rax+190h]
0x1400959e3  cmp     dx, bx
0x1400959e6  jz      loc_140095BB5
0x1400959ec  xor     al, al
0x1400959ee  mov     [rdi+90h], al
0x1400959f4  mov     rax, rdx
0x1400959f7  mov     qword ptr [rdi+0F8h], 0
0x140095a02  mov     qword ptr [rdi+10h], 0
0x140095a0a  mov     qword ptr [rdi+20h], 0
0x140095a12  mov     qword ptr [rdi+30h], 0
0x140095a1a  lock xadd cs:UxNextRequestQueueId, rax
0x140095a23  add     rax, rdx
0x140095a26  mov     [rdi+120h], rcx
0x140095a2d  mov     [rdi+78h], rax
0x140095a31  movzx   eax, cs:UlNumberOfLanes
0x140095a38  lea     rdx, [rcx+rax*8]
0x140095a3c  mov     [rdi+108h], rdx
0x140095a43  cmp     qword ptr [rsi], 0
0x140095a47  jnz     loc_140095BCC
0x140095a4d  lea     rax, [rdi+0D8h]
0x140095a54  mov     ebx, 1
0x140095a59  mov     [rax+8], rax
0x140095a5d  lea     rcx, [rdi+40h]
0x140095a61  mov     [rax], rax
0x140095a64  mov     edx, ebx
0x140095a66  lea     rax, [rdi+0E8h]
0x140095a6d  mov     [rax+8], rax
0x140095a71  mov     [rax], rax
0x140095a74  call    UlSiqInitialize
0x140095a79  mov     [rdi], ebx
0x140095a7b  call    cs:__imp_PsGetCurrentServerSilo
0x140095a82  nop     dword ptr [rax+rax+00h]
0x140095a87  mov     edx, 4F416C55h
0x140095a8c  lea     r8d, [rbx+3Bh]
0x140095a90  mov     rcx, rax
0x140095a93  mov     [rdi+140h], rax
0x140095a9a  call    UxPodReferenceSilo
0x140095a9f  xor     ecx, ecx
0x140095aa1  mov     [rdi+148h], r12
0x140095aa8  call    cs:__imp_ExAllocateCacheAwarePushLock
0x140095aaf  nop     dword ptr [rax+rax+00h]
0x140095ab4  mov     [rdi+118h], rax
0x140095abb  test    rax, rax
0x140095abe  jz      loc_140095B45
0x140095ac4  lea     rcx, [rdi+98h]; NewDescriptor
0x140095acb  mov     rdx, rbp
0x140095ace  call    UlAssignSecurity
0x140095ad3  mov     esi, eax
0x140095ad5  test    eax, eax
0x140095ad7  js      short loc_140095AFE
0x140095ad9  mov     r9, [rdi+120h]
0x140095ae0  mov     r12d, 0C0h
0x140095ae6  mov     ecx, r12d
0x140095ae9  mov     r8d, 4C416C55h
0x140095aef  call    UlAllocatePerNode
0x140095af4  mov     esi, eax
0x140095af6  test    eax, eax
0x140095af8  jns     loc_140095C01
0x140095afe  or      eax, 0FFFFFFFFh
0x140095b01  lock xadd [rdi], eax
0x140095b05  dec     eax
0x140095b07  cmp     cs:UxDebugCheckRefcount, 0
0x140095b0e  jnz     short loc_140095B4C
0x140095b10  mov     rcx, rdi; P
0x140095b13  call    UlFreeRequestQueue
0x140095b18  xor     edi, edi
0x140095b1a  mov     [r15], rdi
0x140095b1d  test    byte ptr cs:xmmword_1401A2CA0+1, bl
0x140095b23  jnz     loc_140095C48
0x140095b29  lea     r11, [rsp+78h+var_28]
0x140095b2e  mov     eax, esi
0x140095b30  mov     rbx, [r11+30h]
0x140095b34  mov     rbp, [r11+40h]
0x140095b38  mov     rsp, r11
0x140095b3b  pop     r15
0x140095b3d  pop     r14
0x140095b3f  pop     r12
0x140095b41  pop     rdi
0x140095b42  pop     rsi
0x140095b43  retn
0x140095b45  mov     esi, 0C000009Ah
0x140095b4a  jmp     short loc_140095AFE
0x140095b4c  cmp     eax, 0FFFFFFFFh
0x140095b4f  jg      short loc_140095B10
0x140095b51  movsxd  r9, eax; BugCheckParameter4
0x140095b54  mov     r8, rbx; BugCheckParameter3
0x140095b57  mov     rdx, rdi; BugCheckParameter2
0x140095b5a  mov     ecx, 3; BugCheckParameter1
0x140095b5f  call    UlBugCheckEx
0x140095b65  mov     rax, [rsi]
0x140095b68  mov     r9d, ebx
0x140095b6b  mov     [rsp+78h+var_38], r15
0x140095b70  shr     r9d, 10h
0x140095b74  mov     [rsp+78h+var_40], rbp
0x140095b79  mov     [rsp+78h+var_48], rax
0x140095b7e  mov     [rsp+78h+var_50], r9d
0x140095b83  mov     r9, r12
0x140095b86  movzx   edx, bx
0x140095b89  mov     [rsp+78h+var_58], edx
0x140095b8d  call    WPP_SF_qllSqq
0x140095b92  mov     r8d, 1
0x140095b98  jmp     loc_140095978
0x140095b9d  movzx   eax, word ptr [r14]
0x140095ba1  add     ecx, 2
0x140095ba4  add     ecx, eax
0x140095ba6  jmp     loc_140095996
0x140095bab  mov     esi, 0C000009Ah
0x140095bb0  jmp     loc_14017BDDA
0x140095bb5  xor     eax, eax
0x140095bb7  cmp     ax, word ptr [rsp+78h+arg_8+2]
0x140095bbf  jnz     loc_1400959EC
0x140095bc5  mov     al, dl
0x140095bc7  jmp     loc_1400959EE
0x140095bcc  lea     rax, [rdx+rax*8]
0x140095bd0  mov     rdx, r14; SourceString
0x140095bd3  mov     [rdi+0A8h], rax
0x140095bda  lea     rcx, [rdi+0A0h]; DestinationString
0x140095be1  movzx   eax, word ptr [r14]
0x140095be5  add     ax, 2
0x140095be9  mov     [rdi+0A2h], ax
0x140095bf0  call    cs:__imp_RtlCopyUnicodeString
0x140095bf7  nop     dword ptr [rax+rax+00h]
0x140095bfc  jmp     loc_140095A4D
0x140095c01  mov     r9, [rdi+108h]
0x140095c08  mov     ecx, 20h ; ' '
0x140095c0d  mov     r8d, 55436C55h
0x140095c13  call    UlAllocatePerNode
0x140095c18  mov     esi, eax
0x140095c1a  test    eax, eax
0x140095c1c  js      loc_140095AFE
0x140095c22  mov     r14, 0FFFFF78000000320h
0x140095c2c  xor     ebp, ebp
0x140095c2e  xor     eax, eax
0x140095c30  mov     r14, [r14]
0x140095c33  cmp     ax, cs:UlNumberOfLanes
0x140095c3a  jnb     loc_140095B1A
0x140095c40  mov     r15, rbx
0x140095c43  jmp     loc_14017BDE4
0x140095c48  mov     edx, 37h ; '7'
0x140095c4d  mov     [rsp+78h+var_58], esi
0x140095c51  mov     ecx, 408h
0x140095c56  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140095c5d  mov     r9, rdi
0x140095c60  call    WPP_SF_qD
0x140095c65  jmp     loc_140095B29
0x14017bdd2  mov     r15, [rsp+78h+arg_20]
0x14017bdda  mov     ebx, 1
0x14017bddf  jmp     loc_140095B1A
0x14017bde4  mov     rcx, [rdi+108h]
0x14017bdeb  movzx   ebx, bp
0x14017bdee  mov     rcx, [rcx+rbx*8]
0x14017bdf2  call    UlInitializeAnchor
0x14017bdf7  mov     rax, [rdi+120h]
0x14017bdfe  mov     r8, r12; Size
0x14017be01  xor     edx, edx; Val
0x14017be03  mov     rbx, [rax+rbx*8]
0x14017be07  mov     rcx, rbx; void *
0x14017be0a  call    memset
0x14017be0f  mov     rcx, rbx; SpinLock
0x14017be12  call    cs:__imp_KeInitializeSpinLock
0x14017be19  nop     dword ptr [rax+rax+00h]
0x14017be1e  movzx   r8d, cs:UlNumberOfLanes
0x14017be26  lea     rax, [rbx+8]
0x14017be2a  mov     [rbx+10h], rax
0x14017be2e  xor     edx, edx
0x14017be30  mov     [rax], rax
0x14017be33  add     bp, r15w
0x14017be37  lea     rax, [rbx+18h]
0x14017be3b  mov     [rbx+20h], rax
0x14017be3f  mov     [rax], rax
0x14017be42  lea     rax, [rbx+58h]
0x14017be46  mov     [rbx+60h], rax
0x14017be4a  mov     [rax], rax
0x14017be4d  lea     rax, [rbx+30h]
0x14017be51  mov     [rbx+38h], rax
0x14017be55  mov     [rax], rax
0x14017be58  lea     rax, [rbx+40h]
0x14017be5c  mov     [rbx+48h], rax
0x14017be60  mov     [rax], rax
0x14017be63  mov     eax, 3E8h
0x14017be68  div     r8d
0x14017be6b  mov     dword ptr [rbx+68h], 3E8h
0x14017be72  mov     [rbx+6Ch], eax
0x14017be75  mov     [rbx+70h], eax
0x14017be78  mov     [rbx+78h], r14
0x14017be7c  cmp     bp, r8w
0x14017be80  jb      loc_14017BDE4
0x14017be86  jmp     loc_14017BDD2
```
