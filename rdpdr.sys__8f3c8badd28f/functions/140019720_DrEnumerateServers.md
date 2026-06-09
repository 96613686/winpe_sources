# DrEnumerateServers

- ea: `0x140019720`
- end: `0x140019a9b`
- name: `DrEnumerateServers`
- size: `891`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14002acc0`

## callees

- `0x1400016a0`
- `0x14000327c`
- `0x1400064b0`
- `0x140011bfc`
- `0x140011c60`
- `0x140011ce4`
- `0x140018b88`
- `0x140019720`
- `0x140027f30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140019866`
- `ntoskrnl!ExAllocatePool2` at `0x140019866`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019a58`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019a58`
- `ntoskrnl!ProbeForWrite` at `0x1400197dd`
- `ntoskrnl!ProbeForWrite` at `0x1400197f5`
- `ntoskrnl!ProbeForWrite` at `0x1400197dd`
- `ntoskrnl!ProbeForWrite` at `0x1400197f5`

## pseudocode

```c
__int64 __fastcall DrEnumerateServers(__int64 a1)
{
  char *v1; // rsi
  SIZE_T v2; // r14
  __int64 v3; // r12
  __int64 v4; // rax
  unsigned int *v5; // r13
  int v6; // edi
  unsigned int v7; // ecx
  char *v8; // r15
  char *Pool2; // rax
  unsigned int *v11; // rcx
  unsigned int ULongFromUser; // eax
  unsigned int *v13; // rcx
  unsigned int v14; // eax
  int v15; // esi
  struct _RX_CONTEXT *v16; // rcx
  struct DrSession *v17; // r9
  int *v18; // rcx
  char *v19; // [rsp+40h] [rbp-78h]
  int v20; // [rsp+6Ch] [rbp-4Ch]
  unsigned int v21[18]; // [rsp+70h] [rbp-48h] BYREF
  unsigned int v22; // [rsp+C0h] [rbp+8h]
  __int64 v23; // [rsp+C8h] [rbp+10h] BYREF
  char *v24; // [rsp+D0h] [rbp+18h] BYREF
  char *v25; // [rsp+D8h] [rbp+20h] BYREF

  v1 = *(char **)(a1 + 560);
  v19 = v1;
  v2 = *(unsigned int *)(a1 + 572);
  v25 = v1;
  v24 = &v1[v2];
  v23 = 0;
  if ( !(_DWORD)v2 )
  {
    v25 = 0;
    v24 = 0;
  }
  if ( (*(_BYTE *)(a1 + 540) & 3) != 3 || (v3 = a1 + 40, v4 = *(_QWORD *)(a1 + 40), *(_QWORD *)(v4 + 8)) )
  {
    SmartPtr<DrFile>::~SmartPtr<DrFile>(&v23);
    return 3221225488LL;
  }
  else
  {
    v5 = *(unsigned int **)(a1 + 552);
    if ( !v5 || !v1 )
    {
LABEL_12:
      SmartPtr<DrFile>::~SmartPtr<DrFile>(&v23);
      return 3221225485LL;
    }
    v6 = 0;
    v7 = *(_DWORD *)(a1 + 568);
    v22 = v7;
    v8 = 0;
    if ( *(_BYTE *)(v4 + 64) )
    {
      ProbeForWrite(v5, v7, 1u);
      ProbeForWrite(v1, v2, 1u);
      if ( (unsigned int)v2 > 0xA0000 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            41,
            WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids,
            (unsigned int)v2);
        goto LABEL_12;
      }
      if ( (_DWORD)v2 )
      {
        Pool2 = (char *)ExAllocatePool2(64, v2, 1917088324);
        v8 = Pool2;
        if ( !Pool2 )
        {
          SmartPtr<DrFile>::~SmartPtr<DrFile>(&v23);
          return 3221225626LL;
        }
        v25 = Pool2;
        v24 = &Pool2[v2];
      }
      v7 = v22;
    }
    if ( v7 >= 0x18 )
    {
      *(_QWORD *)v21 = 0;
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
        RtlReadULongFromUser(v5);
      v11 = v5 + 5;
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
        ULongFromUser = RtlReadULongFromUser(v11);
      else
        ULongFromUser = *v11;
      v21[1] = ULongFromUser;
      v13 = v5 + 1;
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
        v14 = RtlReadULongFromUser(v13);
      else
        v14 = *v13;
      v15 = 0;
      v20 = 0;
      v21[0] = 0;
      if ( (unsigned int)DrSessionManager::FindSessionById(WPP_MAIN_CB.Queue.Wcb.DeviceContext, v14, &v23) )
      {
        v20 = 1;
        if ( DrPackServerEntry(v16, &v25, &v24, v17, v21) )
        {
          v15 = 1;
          v6 = 0;
        }
        else
        {
          v6 = -1073741789;
          v15 = 0;
        }
      }
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
        RtlWriteULongToUser(v5 + 2, v15);
      else
        v5[2] = v15;
      v18 = (int *)(v5 + 3);
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
        RtlWriteULongToUser(v18, v20);
      else
        *v18 = v20;
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
        RtlWriteULongToUser(v5 + 4, v21[0]);
      else
        v5[4] = v21[0];
      v1 = v19;
    }
    else
    {
      v6 = -1073741789;
    }
    if ( v8 )
    {
      if ( v6 >= 0 )
      {
        if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
          RtlCopyToUser(v1, v8, v2);
        else
          RtlCopyVolatileMemory(v1, v8, v2);
      }
      ExFreePoolWithTag(v8, 0);
    }
    SmartPtr<DrFile>::~SmartPtr<DrFile>(&v23);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x140019720  mov     r11, rsp
0x140019723  push    rbx
0x140019724  push    rsi
0x140019725  push    rdi
0x140019726  push    r12
0x140019728  push    r13
0x14001972a  push    r14
0x14001972c  push    r15
0x14001972e  sub     rsp, 80h
0x140019735  mov     rsi, [rcx+230h]
0x14001973c  mov     [rsp+0B8h+var_78], rsi
0x140019741  mov     r14d, [rcx+23Ch]
0x140019748  mov     [r11+20h], rsi
0x14001974c  lea     rax, [r14+rsi]
0x140019750  mov     [r11+18h], rax
0x140019754  xor     ebx, ebx
0x140019756  mov     [r11+10h], rbx
0x14001975a  test    r14d, r14d
0x14001975d  jnz     short loc_140019767
0x14001975f  mov     [r11+20h], rbx
0x140019763  mov     [r11+18h], rbx
0x140019767  mov     eax, [rcx+21Ch]
0x14001976d  and     eax, 3
0x140019770  cmp     al, 3
0x140019772  jnz     loc_140019A75
0x140019778  lea     r12, [rcx+28h]
0x14001977c  mov     rax, [r12]
0x140019780  cmp     [rax+8], rbx
0x140019784  jnz     loc_140019A75
0x14001978a  mov     r13, [rcx+228h]
0x140019791  test    r13, r13
0x140019794  jz      loc_14001983C
0x14001979a  test    rsi, rsi
0x14001979d  jz      loc_14001983C
0x1400197a3  mov     [rsp+0B8h+var_70], rsi
0x1400197a8  mov     [rsp+0B8h+var_68], r14
0x1400197ad  mov     [rsp+0B8h+var_60], r12
0x1400197b2  mov     edi, ebx
0x1400197b4  mov     ecx, [rcx+238h]
0x1400197ba  mov     [rsp+0B8h+arg_0], ecx
0x1400197c1  mov     r15, rbx
0x1400197c4  mov     [rsp+0B8h+var_80], rbx
0x1400197c9  cmp     [rax+40h], bl
0x1400197cc  jz      loc_1400198CA
0x1400197d2  mov     edx, ecx; Length
0x1400197d4  mov     r8d, 1; Alignment
0x1400197da  mov     rcx, r13; Address
0x1400197dd  call    cs:__imp_ProbeForWrite
0x1400197e4  nop     dword ptr [rax+rax+00h]
0x1400197e9  mov     r8d, 1; Alignment
0x1400197ef  mov     rdx, r14; Length
0x1400197f2  mov     rcx, rsi; Address
0x1400197f5  call    cs:__imp_ProbeForWrite
0x1400197fc  nop     dword ptr [rax+rax+00h]
0x140019801  nop
0x140019802  cmp     r14d, 0A0000h
0x140019809  jbe     short loc_140019853
0x14001980b  lea     rax, WPP_GLOBAL_Control
0x140019812  mov     rcx, cs:WPP_GLOBAL_Control
0x140019819  cmp     rcx, rax
0x14001981c  jz      short loc_14001983C
0x14001981e  cmp     byte ptr [rcx+29h], 2
0x140019822  jb      short loc_14001983C
0x140019824  mov     edx, 29h ; ')'
0x140019829  mov     r9d, r14d
0x14001982c  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x140019833  mov     rcx, [rcx+18h]
0x140019837  call    WPP_SF_d
0x14001983c  lea     rcx, [rsp+0B8h+arg_8]
0x140019844  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140019849  mov     eax, 0C000000Dh
0x14001984e  jmp     loc_140019A87
0x140019853  test    r14d, r14d
0x140019856  jz      short loc_1400198C3
0x140019858  mov     r8d, 72447244h
0x14001985e  mov     rdx, r14
0x140019861  mov     ecx, 40h ; '@'
0x140019866  call    cs:__imp_ExAllocatePool2
0x14001986d  nop     dword ptr [rax+rax+00h]
0x140019872  mov     r15, rax
0x140019875  mov     [rsp+0B8h+var_80], rax
0x14001987a  test    rax, rax
0x14001987d  jnz     short loc_140019896
0x14001987f  lea     rcx, [rsp+0B8h+arg_8]
0x140019887  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14001988c  mov     eax, 0C000009Ah
0x140019891  jmp     loc_140019A87
0x140019896  mov     [rsp+0B8h+arg_18], rax
0x14001989e  lea     rax, [r14+rax]
0x1400198a2  mov     [rsp+0B8h+arg_10], rax
0x1400198aa  jmp     short loc_1400198C3
0x1400198ac  lea     rcx, [rsp+0B8h+arg_8]
0x1400198b4  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x1400198b9  mov     eax, 0C000000Dh
0x1400198be  jmp     loc_140019A87
0x1400198c3  mov     ecx, [rsp+0B8h+arg_0]
0x1400198ca  cmp     ecx, 18h
0x1400198cd  jnb     short loc_1400198DD
0x1400198cf  mov     edi, 0C0000023h
0x1400198d4  mov     [rsp+0B8h+var_88], edi
0x1400198d8  jmp     loc_140019A20
0x1400198dd  xorps   xmm0, xmm0
0x1400198e0  xor     eax, eax
0x1400198e2  movups  [rsp+0B8h+var_58], xmm0
0x1400198e7  mov     qword ptr [rsp+0B8h+var_48], rax
0x1400198ec  mov     rax, [r12]
0x1400198f0  cmp     [rax+40h], bl
0x1400198f3  jz      short loc_1400198FF
0x1400198f5  mov     rcx, r13
0x1400198f8  call    RtlReadULongFromUser
0x1400198fd  jmp     short loc_140019903
0x1400198ff  mov     eax, [r13+0]
0x140019903  mov     dword ptr [rsp+0B8h+var_58], eax
0x140019907  lea     rcx, [r13+14h]
0x14001990b  mov     rax, [r12]
0x14001990f  cmp     [rax+40h], bl
0x140019912  jz      short loc_14001991B
0x140019914  call    RtlReadULongFromUser
0x140019919  jmp     short loc_14001991D
0x14001991b  mov     eax, [rcx]
0x14001991d  mov     [rsp+0B8h+var_48+4], eax
0x140019921  lea     rcx, [r13+4]
0x140019925  mov     rax, [r12]
0x140019929  cmp     [rax+40h], bl
0x14001992c  jz      short loc_140019935
0x14001992e  call    RtlReadULongFromUser
0x140019933  jmp     short loc_140019937
0x140019935  mov     eax, [rcx]
0x140019937  mov     dword ptr [rsp+0B8h+var_58+4], eax
0x14001993b  mov     esi, ebx
0x14001993d  mov     qword ptr [rsp+0B8h+var_58+8], rbx
0x140019942  mov     [rsp+0B8h+var_48], ebx
0x140019946  lea     r8, [rsp+0B8h+arg_8]
0x14001994e  mov     edx, eax
0x140019950  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+20h
0x140019957  call    ?FindSessionById@DrSessionManager@@QEAAHKAEAV?$SmartPtr@VDrSession@@@@@Z; DrSessionManager::FindSessionById(ulong,SmartPtr<DrSession> &)
0x14001995c  test    eax, eax
0x14001995e  jz      short loc_1400199AA
0x140019960  mov     dword ptr [rsp+0B8h+var_58+0Ch], 1
0x140019968  lea     rax, [rsp+0B8h+var_48]
0x14001996d  mov     [rsp+0B8h+var_98], rax; unsigned int *
0x140019972  lea     r8, [rsp+0B8h+arg_10]; char **
0x14001997a  lea     rdx, [rsp+0B8h+arg_18]; char **
0x140019982  call    ?DrPackServerEntry@@YAEPEAU_RX_CONTEXT@@PEAPEAD1PEAVDrSession@@PEAK@Z; DrPackServerEntry(_RX_CONTEXT *,char * *,char * *,DrSession *,ulong *)
0x140019987  test    al, al
0x140019989  jz      short loc_14001999D
0x14001998b  mov     esi, dword ptr [rsp+0B8h+var_58+8]
0x14001998f  inc     esi
0x140019991  mov     dword ptr [rsp+0B8h+var_58+8], esi
0x140019995  mov     edi, ebx
0x140019997  mov     [rsp+0B8h+var_88], ebx
0x14001999b  jmp     short loc_1400199AA
0x14001999d  mov     edi, 0C0000023h
0x1400199a2  mov     [rsp+0B8h+var_88], edi
0x1400199a6  mov     esi, dword ptr [rsp+0B8h+var_58+8]
0x1400199aa  mov     rax, [r12]
0x1400199ae  cmp     [rax+40h], bl
0x1400199b1  jz      short loc_1400199C0
0x1400199b3  mov     edx, esi
0x1400199b5  lea     rcx, [r13+8]
0x1400199b9  call    RtlWriteULongToUser
0x1400199be  jmp     short loc_1400199C4
0x1400199c0  mov     [r13+8], esi
0x1400199c4  mov     edx, dword ptr [rsp+0B8h+var_58+0Ch]
0x1400199c8  lea     rcx, [r13+0Ch]
0x1400199cc  mov     rax, [r12]
0x1400199d0  cmp     [rax+40h], bl
0x1400199d3  jz      short loc_1400199DC
0x1400199d5  call    RtlWriteULongToUser
0x1400199da  jmp     short loc_1400199DE
0x1400199dc  mov     [rcx], edx
0x1400199de  mov     edx, [rsp+0B8h+var_48]
0x1400199e2  mov     rax, [r12]
0x1400199e6  cmp     [rax+40h], bl
0x1400199e9  jz      short loc_1400199F6
0x1400199eb  lea     rcx, [r13+10h]
0x1400199ef  call    RtlWriteULongToUser
0x1400199f4  jmp     short loc_1400199FA
0x1400199f6  mov     [r13+10h], edx
0x1400199fa  mov     rsi, [rsp+0B8h+var_78]
0x1400199ff  jmp     short loc_140019A20
0x140019a01  mov     edi, 0C000000Dh
0x140019a06  mov     [rsp+0B8h+var_88], edi
0x140019a0a  xor     ebx, ebx
0x140019a0c  mov     rsi, [rsp+0B8h+var_70]
0x140019a11  mov     r15, [rsp+0B8h+var_80]
0x140019a16  mov     r14, [rsp+0B8h+var_68]
0x140019a1b  mov     r12, [rsp+0B8h+var_60]
0x140019a20  test    r15, r15
0x140019a23  jz      short loc_140019A64
0x140019a25  test    edi, edi
0x140019a27  js      short loc_140019A53
0x140019a29  mov     rax, [r12]
0x140019a2d  mov     r8, r14; Size
0x140019a30  mov     rdx, r15; Src
0x140019a33  mov     rcx, rsi; void *
0x140019a36  cmp     [rax+40h], bl
0x140019a39  jz      short loc_140019A42
0x140019a3b  call    RtlCopyToUser
0x140019a40  jmp     short loc_140019A47
0x140019a42  call    RtlCopyVolatileMemory
0x140019a47  jmp     short loc_140019A53
0x140019a49  mov     edi, 0C000000Dh
0x140019a4e  mov     r15, [rsp+0B8h+var_80]
0x140019a53  xor     edx, edx; Tag
0x140019a55  mov     rcx, r15; P
0x140019a58  call    cs:__imp_ExFreePoolWithTag
0x140019a5f  nop     dword ptr [rax+rax+00h]
0x140019a64  lea     rcx, [rsp+0B8h+arg_8]
0x140019a6c  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140019a71  mov     eax, edi
0x140019a73  jmp     short loc_140019A87
0x140019a75  lea     rcx, [rsp+0B8h+arg_8]
0x140019a7d  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140019a82  mov     eax, 0C0000010h
0x140019a87  add     rsp, 80h
0x140019a8e  pop     r15
0x140019a90  pop     r14
0x140019a92  pop     r13
0x140019a94  pop     r12
0x140019a96  pop     rdi
0x140019a97  pop     rsi
0x140019a98  pop     rbx
0x140019a99  retn
```
