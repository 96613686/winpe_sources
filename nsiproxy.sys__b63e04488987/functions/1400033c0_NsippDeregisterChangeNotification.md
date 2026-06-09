# NsippDeregisterChangeNotification

- ea: `0x1400033c0`
- end: `0x1400036ec`
- name: `NsippDeregisterChangeNotification`
- size: `812`
- prototype: `__int64 __fastcall(void *Src, unsigned int, unsigned __int8, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140001dd0`
- `0x140002090`

## callees

- `0x1400033c0`
- `0x1400043d0`
- `0x140004d70`
- `0x1400056e8`
- `0x140006560`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003537`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003537`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400035b1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400035b1`
- `ntoskrnl!IoIs32bitProcess` at `0x140003407`
- `ntoskrnl!IoIs32bitProcess` at `0x140003407`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400035ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400036d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400035ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400036d1`
- `NETIO!NsiDeregisterChangeNotificationEx` at `0x1400035d7`
- `NETIO!NsiDeregisterChangeNotificationEx` at `0x1400035d7`

## pseudocode

```c
__int64 __fastcall NsippDeregisterChangeNotification(void *Src, unsigned int a2, unsigned __int8 a3, __int64 a4)
{
  BOOLEAN v8; // al
  int v9; // ebx
  __int64 *v10; // r12
  _QWORD *v11; // r14
  __int64 *v12; // rdi
  KIRQL v13; // r13
  __int64 *i; // rbx
  __int64 *v15; // rax
  __int64 **v16; // rcx
  PVOID P; // [rsp+D0h] [rbp-98h] BYREF
  char *v19; // [rsp+D8h] [rbp-90h] BYREF
  _OWORD v20[2]; // [rsp+E0h] [rbp-88h] BYREF
  __int128 v21; // [rsp+100h] [rbp-68h] BYREF
  __int128 v22; // [rsp+110h] [rbp-58h]
  int v23; // [rsp+120h] [rbp-48h]

  P = 0;
  v19 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v8 = IoIs32bitProcess(0);
  if ( !Src )
    return 3221225485LL;
  if ( v8 )
  {
    if ( a2 >= 0x20 )
    {
      memset(v20, 0, 28);
      if ( a3 )
        RtlCopyFromUser(v20, Src, 0x20u);
      else
        RtlCopyVolatileMemory(v20, Src, 0x20u);
      *((_QWORD *)&v21 + 1) = *((_QWORD *)&v20[0] + 1);
      LODWORD(v21) = v20[0];
      LODWORD(v22) = v20[1];
      *((_QWORD *)&v22 + 1) = SDWORD2(v20[1]);
      goto LABEL_7;
    }
    return 3221225485LL;
  }
  if ( a2 < 0x28 )
    return 3221225485LL;
  if ( a3 )
    RtlCopyFromUser(&v21, Src, 0x28u);
  else
    RtlCopyVolatileMemory(&v21, Src, 0x28u);
LABEL_7:
  v9 = NsippProbeAndAllocateParameters(
         &v21,
         0x28u,
         (__int64)&v21,
         0,
         0,
         0,
         0,
         0,
         a3,
         1u,
         0,
         0,
         0,
         0,
         0,
         0,
         0,
         0,
         0,
         0,
         0,
         0,
         0,
         &v19,
         &P);
  if ( v9 < 0 )
  {
    v11 = P;
  }
  else
  {
    v10 = 0;
    v11 = P;
    *((_QWORD *)P + 1) = v19;
    v12 = *(__int64 **)(*(_QWORD *)(a4 + 48) + 24LL);
    v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v12 + 3);
    for ( i = (__int64 *)*v12; i != v12; i = (__int64 *)*i )
    {
      if ( !*((_DWORD *)i + 4) )
      {
        v10 = i;
        if ( (unsigned __int8)NsippIsMatchingObject(i + 3, v11) == 1
          && (!a3 && i[6] == v11[3] || a3 == 1 && i == (__int64 *)v11[3]) )
        {
          v15 = (__int64 *)*i;
          if ( *(__int64 **)(*i + 8) != i || (v16 = (__int64 **)i[1], *v16 != i) )
            __fastfail(3u);
          *v16 = v15;
          v15[1] = (__int64)v16;
          break;
        }
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)v12 + 3, v13);
    if ( i == v12 )
    {
      v9 = -1073741811;
    }
    else
    {
      if ( a3 == 1 )
        v11[3] = 0;
      v9 = NsiDeregisterChangeNotificationEx(v11);
      ExFreePoolWithTag(v10, 0);
    }
  }
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400033c0  mov     r11, rsp
0x1400033c3  push    rbx
0x1400033c4  push    rsi
0x1400033c5  push    rdi
0x1400033c6  push    r12
0x1400033c8  push    r13
0x1400033ca  push    r14
0x1400033cc  push    r15
0x1400033ce  sub     rsp, 130h
0x1400033d5  mov     rsi, r9
0x1400033d8  movzx   r15d, r8b
0x1400033dc  mov     ebx, edx
0x1400033de  mov     rdi, rcx
0x1400033e1  xor     r14d, r14d
0x1400033e4  mov     [r11-98h], r14
0x1400033eb  mov     [r11-90h], r14
0x1400033f2  xor     eax, eax
0x1400033f4  xorps   xmm0, xmm0
0x1400033f7  movups  xmmword ptr [r11-68h], xmm0
0x1400033fc  movups  xmmword ptr [r11-58h], xmm0
0x140003401  mov     [r11-48h], eax
0x140003405  xor     ecx, ecx; Irp
0x140003407  call    cs:__imp_IoIs32bitProcess
0x14000340e  nop     dword ptr [rax+rax+00h]
0x140003413  test    rdi, rdi
0x140003416  jz      loc_1400036E2
0x14000341c  test    al, al
0x14000341e  jnz     loc_14000367C
0x140003424  cmp     ebx, 28h ; '('
0x140003427  jb      loc_1400036E2
0x14000342d  mov     r8d, 28h ; '('; Size
0x140003433  mov     rdx, rdi; Src
0x140003436  lea     rcx, [rsp+168h+var_68]; void *
0x14000343e  test    r15b, r15b
0x140003441  jz      short loc_14000344A
0x140003443  call    RtlCopyFromUser
0x140003448  jmp     short loc_14000344F
0x14000344a  call    RtlCopyVolatileMemory
0x14000344f  jmp     short loc_140003456
0x140003451  jmp     loc_140003601
0x140003456  lea     rax, [rsp+168h+P]
0x14000345e  mov     [rsp+168h+var_A8], rax
0x140003466  lea     rax, [rsp+168h+var_90]
0x14000346e  mov     [rsp+168h+var_B0], rax
0x140003476  mov     [rsp+168h+var_B8], r14
0x14000347e  mov     [rsp+168h+var_C0], r14
0x140003486  mov     [rsp+168h+var_C8], r14
0x14000348e  mov     [rsp+168h+var_D0], r14
0x140003496  mov     [rsp+168h+var_D8], r14
0x14000349e  mov     [rsp+168h+var_E0], r14
0x1400034a6  mov     [rsp+168h+var_E8], r14
0x1400034ae  mov     [rsp+168h+var_F0], r14
0x1400034b3  mov     [rsp+168h+var_F8], r14
0x1400034b8  mov     [rsp+168h+var_100], r14
0x1400034bd  mov     [rsp+168h+var_108], r14
0x1400034c2  mov     [rsp+168h+var_110], r14
0x1400034c7  mov     [rsp+168h+var_118], 0
0x1400034cc  mov     [rsp+168h+var_120], 1
0x1400034d4  mov     [rsp+168h+var_128], r15b
0x1400034d9  mov     [rsp+168h+var_130], r14
0x1400034de  mov     [rsp+168h+var_138], r14
0x1400034e3  mov     [rsp+168h+var_140], r14
0x1400034e8  mov     [rsp+168h+var_148], r14
0x1400034ed  xor     r9d, r9d
0x1400034f0  lea     r8, [rsp+168h+var_68]
0x1400034f8  mov     edx, 28h ; '('
0x1400034fd  lea     rcx, [rsp+168h+var_68]
0x140003505  call    NsippProbeAndAllocateParameters
0x14000350a  mov     ebx, eax
0x14000350c  test    eax, eax
0x14000350e  js      loc_1400036BF
0x140003514  mov     r12, r14
0x140003517  mov     r14, [rsp+168h+P]
0x14000351f  mov     rax, [rsp+168h+var_90]
0x140003527  mov     [r14+8], rax
0x14000352b  mov     rax, [rsi+30h]
0x14000352f  mov     rdi, [rax+18h]
0x140003533  lea     rcx, [rdi+18h]; SpinLock
0x140003537  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000353e  nop     dword ptr [rax+rax+00h]
0x140003543  movzx   r13d, al
0x140003547  mov     rbx, [rdi]
0x14000354a  nop     word ptr [rax+rax+00h]
0x140003550  cmp     rbx, rdi
0x140003553  jz      short loc_1400035A9
0x140003555  cmp     dword ptr [rbx+10h], 0
0x140003559  jz      short loc_140003560
0x14000355b  mov     rbx, [rbx]
0x14000355e  jmp     short loc_140003550
0x140003560  mov     r12, rbx
0x140003563  lea     rcx, [rbx+18h]
0x140003567  mov     rdx, r14
0x14000356a  call    NsippIsMatchingObject
0x14000356f  cmp     al, 1
0x140003571  jnz     short loc_14000355B
0x140003573  test    r15b, r15b
0x140003576  jz      loc_14000369B
0x14000357c  cmp     r15b, 1
0x140003580  jnz     short loc_14000355B
0x140003582  cmp     rbx, [r14+18h]
0x140003586  jnz     short loc_14000355B
0x140003588  mov     rax, [rbx]
0x14000358b  cmp     [rax+8], rbx
0x14000358f  jnz     loc_1400036AE
0x140003595  mov     rcx, [rbx+8]
0x140003599  cmp     [rcx], rbx
0x14000359c  jnz     loc_1400036AE
0x1400035a2  mov     [rcx], rax
0x1400035a5  mov     [rax+8], rcx
0x1400035a9  movzx   edx, r13b; NewIrql
0x1400035ad  lea     rcx, [rdi+18h]; SpinLock
0x1400035b1  call    cs:__imp_KeReleaseSpinLock
0x1400035b8  nop     dword ptr [rax+rax+00h]
0x1400035bd  cmp     rbx, rdi
0x1400035c0  jz      loc_1400036B5
0x1400035c6  cmp     r15b, 1
0x1400035ca  jnz     short loc_1400035D4
0x1400035cc  mov     qword ptr [r14+18h], 0
0x1400035d4  mov     rcx, r14
0x1400035d7  call    cs:__imp_NsiDeregisterChangeNotificationEx
0x1400035de  nop     dword ptr [rax+rax+00h]
0x1400035e3  mov     ebx, eax
0x1400035e5  xor     edx, edx; Tag
0x1400035e7  mov     rcx, r12; P
0x1400035ea  call    cs:__imp_ExFreePoolWithTag
0x1400035f1  nop     dword ptr [rax+rax+00h]
0x1400035f6  test    r14, r14
0x1400035f9  jnz     loc_1400036CC
0x1400035ff  mov     eax, ebx
0x140003601  add     rsp, 130h
0x140003608  pop     r15
0x14000360a  pop     r14
0x14000360c  pop     r13
0x14000360e  pop     r12
0x140003610  pop     rdi
0x140003611  pop     rsi
0x140003612  pop     rbx
0x140003613  retn
0x140003615  mov     r8d, 20h ; ' '; Size
0x14000361b  mov     rdx, rdi; Src
0x14000361e  lea     rcx, [rsp+168h+var_88]; void *
0x140003626  test    r15b, r15b
0x140003629  jz      short loc_140003632
0x14000362b  call    RtlCopyFromUser
0x140003630  jmp     short loc_140003637
0x140003632  call    RtlCopyVolatileMemory
0x140003637  jmp     short loc_14000363B
0x140003639  jmp     short loc_140003601
0x14000363b  mov     rax, qword ptr [rsp+168h+var_88+8]
0x140003643  mov     [rsp+168h+var_60], rax
0x14000364b  mov     eax, dword ptr [rsp+168h+var_88]
0x140003652  mov     dword ptr [rsp+168h+var_68], eax
0x140003659  mov     eax, [rsp+168h+var_78]
0x140003660  mov     [rsp+168h+var_58], eax
0x140003667  movsxd  rax, [rsp+168h+var_70]
0x14000366f  mov     [rsp+168h+var_50], rax
0x140003677  jmp     loc_140003456
0x14000367c  cmp     ebx, 20h ; ' '
0x14000367f  jb      short loc_1400036E2
0x140003681  xor     eax, eax
0x140003683  xorps   xmm0, xmm0
0x140003686  movups  [rsp+168h+var_88], xmm0
0x14000368e  movups  [rsp+168h+var_88+0Ch], xmm0
0x140003696  jmp     loc_140003615
0x14000369b  mov     rax, [r14+18h]
0x14000369f  cmp     [rbx+30h], rax
0x1400036a3  jz      loc_140003588
0x1400036a9  jmp     loc_14000357C
0x1400036ae  mov     ecx, 3
0x1400036b3  int     29h; Win8: RtlFailFast(ecx)
0x1400036b5  mov     ebx, 0C000000Dh
0x1400036ba  jmp     loc_1400035F6
0x1400036bf  mov     r14, [rsp+168h+P]
0x1400036c7  jmp     loc_1400035F6
0x1400036cc  xor     edx, edx; Tag
0x1400036ce  mov     rcx, r14; P
0x1400036d1  call    cs:__imp_ExFreePoolWithTag
0x1400036d8  nop     dword ptr [rax+rax+00h]
0x1400036dd  jmp     loc_1400035FF
0x1400036e2  mov     eax, 0C000000Dh
0x1400036e7  jmp     loc_140003601
```
