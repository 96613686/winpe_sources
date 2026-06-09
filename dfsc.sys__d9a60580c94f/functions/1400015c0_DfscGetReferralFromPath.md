# DfscGetReferralFromPath

- ea: `0x1400015c0`
- end: `0x14000173d`
- name: `DfscGetReferralFromPath`
- size: `381`
- prototype: `__int64 __fastcall(IRP *, volatile signed __int32 *, IRP *, int, __int64, __int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x140014d30`
- `0x14001520c`
- `0x140015520`
- `0x140015f30`
- `0x140016070`
- `0x140021410`
- `0x1400281ac`

## callees

- `0x1400015c0`
- `0x140002cd0`
- `0x140003904`
- `0x140005fb0`
- `0x140011c80`
- `0x14001abc0`
- `0x14001e3d0`
- `0x14001fb50`
- `0x140020e10`
- `0x140023010`
- `0x140023410`
- `0x1400239b0`
- `0x140026fd0`
- `0x140026fe0`
- `0x1400284a0`

## pseudocode

```c
__int64 __fastcall DfscGetReferralFromPath(
        IRP *a1,
        volatile signed __int32 *a2,
        IRP *a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  int v10; // ebx
  _DWORD *v11; // rdi
  __int64 v12; // rsi
  __int64 v13; // r14
  int v14; // ebx
  int v15; // r8d
  __int16 v16; // r8
  _WORD *v17; // r9
  PVOID P[9]; // [rsp+40h] [rbp-48h] BYREF

  P[0] = 0;
  v10 = DfscCmInitializeContext(a1, a2, a5, a3, 0, a7, P);
  if ( v10 < 0 )
  {
    if ( v10 == -1073741802 )
      return (unsigned int)-1073741772;
  }
  else
  {
    v11 = P[0];
    *((_DWORD *)P[0] + 73) = a4;
    LODWORD(v12) = 0;
    do
    {
      v13 = (int)v12;
      v14 = v12;
      v12 = ((int (__fastcall *)(_DWORD *))DfscCmDispatchTable[(int)v12])(v11);
      v11[78] = v14;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_qDSS(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)WPP_GLOBAL_Control,
          v15,
          (_DWORD)v11,
          v11[79],
          (__int64)DfscStateTextTable[v13],
          (__int64)DfscStateTextTable[v12]);
      }
    }
    while ( (_DWORD)v12 != 10 );
    v10 = v11[79];
    if ( v10 >= 0 )
    {
      *(_QWORD *)a6 = *((_QWORD *)v11 + 34);
      *((_QWORD *)v11 + 34) = 0;
      if ( *(_QWORD *)a6 )
        *(_WORD *)(*(_QWORD *)a6 + 32LL) = -1;
      if ( a8 )
      {
        v16 = *((_WORD *)v11 + 112);
        *(_WORD *)(a8 + 2) = v16;
        *(_WORD *)a8 = v16;
        v17 = (_WORD *)((char *)a3->MdlAddress + (unsigned __int16)a3->Type - *((unsigned __int16 *)v11 + 112));
        *(_QWORD *)(a8 + 8) = v17;
        if ( v16 == 2 && *v17 == 92 )
          *(_WORD *)a8 = 0;
      }
    }
    DfscCmReleaseContext(v11);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400015c0  mov     r11, rsp
0x1400015c3  push    rbx
0x1400015c4  push    rbp
0x1400015c5  push    rsi
0x1400015c6  push    rdi
0x1400015c7  push    r12
0x1400015c9  push    r14
0x1400015cb  sub     rsp, 58h
0x1400015cf  lea     rax, [r11-48h]
0x1400015d3  mov     qword ptr [r11-48h], 0
0x1400015db  mov     [r11-58h], rax
0x1400015df  mov     esi, r9d
0x1400015e2  mov     rax, [rsp+88h+arg_30]
0x1400015ea  mov     rbp, r8
0x1400015ed  mov     r9, r8; int
0x1400015f0  mov     [r11-60h], rax
0x1400015f4  mov     r8, [rsp+88h+arg_20]; int
0x1400015fc  mov     qword ptr [r11-68h], 0
0x140001604  call    DfscCmInitializeContext
0x140001609  mov     ebx, eax
0x14000160b  test    eax, eax
0x14000160d  js      loc_14000171F
0x140001613  mov     rdi, [rsp+88h+P]
0x140001618  lea     r12, cs:140000000h
0x14000161f  mov     [rdi+124h], esi
0x140001625  xor     esi, esi
0x140001627  movsxd  r14, esi
0x14000162a  mov     rcx, rdi
0x14000162d  mov     ebx, esi
0x14000162f  mov     rax, ds:(DfscCmDispatchTable - 140000000h)[r12+r14*8]
0x140001637  call    _guard_dispatch_icall
0x14000163c  movsxd  rsi, eax
0x14000163f  mov     [rdi+138h], ebx
0x140001645  mov     rdx, cs:WPP_GLOBAL_Control
0x14000164c  lea     rax, WPP_GLOBAL_Control
0x140001653  cmp     rdx, rax
0x140001656  jz      short loc_140001691
0x140001658  test    dword ptr [rdx+2Ch], 400000h
0x14000165f  jz      short loc_140001691
0x140001661  mov     rax, ds:rva DfscStateTextTable[r12+rsi*8]
0x140001669  mov     r9, rdi
0x14000166c  mov     rcx, [rdx+18h]
0x140001670  mov     [rsp+88h+var_58], rax
0x140001675  mov     rax, ds:rva DfscStateTextTable[r12+r14*8]
0x14000167d  mov     [rsp+88h+var_60], rax
0x140001682  mov     eax, [rdi+13Ch]
0x140001688  mov     [rsp+88h+var_68], eax
0x14000168c  call    WPP_SF_qDSS
0x140001691  cmp     esi, 0Ah
0x140001694  jnz     short loc_140001627
0x140001696  mov     ebx, [rdi+13Ch]
0x14000169c  test    ebx, ebx
0x14000169e  js      short loc_140001715
0x1400016a0  mov     rax, [rdi+110h]
0x1400016a7  mov     rcx, [rsp+88h+arg_28]
0x1400016af  mov     [rcx], rax
0x1400016b2  mov     qword ptr [rdi+110h], 0
0x1400016bd  mov     rax, [rcx]
0x1400016c0  test    rax, rax
0x1400016c3  jz      short loc_1400016CB
0x1400016c5  mov     word ptr [rax+20h], 0FFFFh
0x1400016cb  mov     rcx, [rsp+88h+arg_38]
0x1400016d3  test    rcx, rcx
0x1400016d6  jz      short loc_140001715
0x1400016d8  movzx   r8d, word ptr [rdi+0E0h]
0x1400016e0  mov     [rcx+2], r8w
0x1400016e5  mov     [rcx], r8w
0x1400016e9  movzx   eax, word ptr [rdi+0E0h]
0x1400016f0  mov     r9, [rbp+8]
0x1400016f4  sub     r9, rax
0x1400016f7  movzx   eax, word ptr [rbp+0]
0x1400016fb  add     r9, rax
0x1400016fe  mov     [rcx+8], r9
0x140001702  cmp     r8w, 2
0x140001707  jnz     short loc_140001715
0x140001709  cmp     word ptr [r9], 5Ch ; '\'
0x14000170e  jnz     short loc_140001715
0x140001710  xor     eax, eax
0x140001712  mov     [rcx], ax
0x140001715  mov     rcx, rdi; P
0x140001718  call    DfscCmReleaseContext
0x14000171d  jmp     short loc_14000172D
0x14000171f  cmp     ebx, 0C0000016h
0x140001725  mov     eax, 0C0000034h
0x14000172a  cmovz   ebx, eax
0x14000172d  mov     eax, ebx
0x14000172f  add     rsp, 58h
0x140001733  pop     r14
0x140001735  pop     r12
0x140001737  pop     rdi
0x140001738  pop     rsi
0x140001739  pop     rbp
0x14000173a  pop     rbx
0x14000173b  retn
```
