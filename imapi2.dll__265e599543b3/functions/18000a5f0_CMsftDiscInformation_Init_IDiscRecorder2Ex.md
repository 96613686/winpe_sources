# CMsftDiscInformation::Init(IDiscRecorder2Ex *)

- ea: `0x18000a5f0`
- end: `0x18000a747`
- name: `?Init@CMsftDiscInformation@@QEAAJPEAUIDiscRecorder2Ex@@@Z`
- size: `343`
- prototype: `__int64 __fastcall(CMsftDiscInformation *__hidden this, struct IDiscRecorder2Ex *)`
- caller_count: `19`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180006ea0`
- `0x180009640`
- `0x180009ab8`
- `0x180009b80`
- `0x180019a00`
- `0x180019dc8`
- `0x18001a3e0`
- `0x18001a4f4`
- `0x18001b104`
- `0x18001c518`
- `0x18001d420`
- `0x18001d70c`
- `0x18001dd30`
- `0x180026638`
- `0x1800301a8`
- `0x180038350`
- `0x1800389f0`
- `0x180039a4c`
- `0x180046bf4`

## callees

- `0x18000a5f0`
- `0x18000a750`
- `0x1800140f4`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000a72c`
- `ole32!CoTaskMemFree` at `0x18000a72c`
- `KERNEL32!Sleep` at `0x18000a67e`
- `KERNEL32!Sleep` at `0x18000a67e`

## pseudocode

```c
__int64 __fastcall CMsftDiscInformation::Init(CMsftDiscInformation *this, struct IDiscRecorder2Ex *a2)
{
  int v4; // ebx
  unsigned int i; // edi
  unsigned int v6; // eax
  void *v7; // rdx
  __int64 v8; // r9
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  int v13; // [rsp+50h] [rbp+18h] BYREF
  LPVOID pv; // [rsp+58h] [rbp+20h] BYREF

  v4 = 0;
  pv = 0;
  v13 = 0;
  for ( i = 0; i < 0xA; ++i )
  {
    v6 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, LPVOID *, int *))a2->lpVtbl->GetDiscInformation)(
           a2,
           &pv,
           &v13);
    v4 = v6;
    if ( ((v6 + 1062600187) & 0xFFFFFFFD) != 0 )
      break;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_7fbbfb794ace3f4195f7fb7939ddc37a_Traceguids, v6);
    }
    Sleep(0x2710u);
  }
  if ( v4 < 0 )
    goto LABEL_24;
  v7 = pv;
  if ( pv
    && v13 >= 2
    && (unsigned __int64)v13 >= 9
    && v13 == (*((unsigned __int8 *)pv + 1) | (*(unsigned __int8 *)pv << 8)) + 2 )
  {
    v11 = CMsftDiscInformation::Init(this, (unsigned __int8 *)pv, v13);
    v4 = v11;
    if ( v11 >= 0 )
      goto LABEL_24;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_24;
    }
    v10 = 12;
    v8 = (unsigned int)v11;
LABEL_23:
    WPP_SF_d(v9[2], v10, WPP_7fbbfb794ace3f4195f7fb7939ddc37a_Traceguids, v8);
LABEL_24:
    v7 = pv;
    goto LABEL_25;
  }
  v4 = -1062599937;
  v8 = 3232367359LL;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v10 = 11;
    goto LABEL_23;
  }
LABEL_25:
  CoTaskMemFree(v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000a5f0  mov     rax, rsp
0x18000a5f3  mov     [rax+8], rbx
0x18000a5f7  mov     [rax+10h], rbp
0x18000a5fb  push    rsi
0x18000a5fc  push    rdi
0x18000a5fd  push    r12
0x18000a5ff  sub     rsp, 20h
0x18000a603  mov     rsi, rdx
0x18000a606  mov     rbp, rcx
0x18000a609  xor     ebx, ebx
0x18000a60b  mov     [rax+20h], rbx
0x18000a60f  mov     [rax+18h], ebx
0x18000a612  xor     edi, edi
0x18000a614  lea     r12, WPP_GLOBAL_Control
0x18000a61b  cmp     edi, 0Ah
0x18000a61e  jnb     short loc_18000A688
0x18000a620  mov     rax, [rsi]
0x18000a623  lea     r8, [rsp+38h+arg_10]
0x18000a628  lea     rdx, [rsp+38h+pv]
0x18000a62d  mov     rcx, rsi
0x18000a630  mov     rax, [rax+50h]
0x18000a634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a639  mov     ebx, eax
0x18000a63b  lea     ecx, [rax+3F55FDFBh]
0x18000a641  test    ecx, 0FFFFFFFDh
0x18000a647  jnz     short loc_18000A688
0x18000a649  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a650  cmp     rcx, r12
0x18000a653  jz      short loc_18000A679
0x18000a655  test    byte ptr [rcx+1Ch], 4
0x18000a659  jz      short loc_18000A679
0x18000a65b  cmp     byte ptr [rcx+19h], 3
0x18000a65f  jb      short loc_18000A679
0x18000a661  mov     edx, 0Ah
0x18000a666  mov     r9d, eax
0x18000a669  lea     r8, WPP_7fbbfb794ace3f4195f7fb7939ddc37a_Traceguids
0x18000a670  mov     rcx, [rcx+10h]
0x18000a674  call    WPP_SF_d
0x18000a679  mov     ecx, 2710h; dwMilliseconds
0x18000a67e  call    cs:__imp_Sleep
0x18000a684  inc     edi
0x18000a686  jmp     short loc_18000A61B
0x18000a688  test    ebx, ebx
0x18000a68a  js      loc_18000A724
0x18000a690  mov     rdx, [rsp+38h+pv]; unsigned __int8 *
0x18000a695  test    rdx, rdx
0x18000a698  jz      short loc_18000A6BF
0x18000a69a  movsxd  r8, [rsp+38h+arg_10]; int
0x18000a69f  cmp     r8d, 2
0x18000a6a3  jl      short loc_18000A6BF
0x18000a6a5  cmp     r8, 9
0x18000a6a9  jb      short loc_18000A6BF
0x18000a6ab  movzx   ecx, byte ptr [rdx]
0x18000a6ae  shl     ecx, 8
0x18000a6b1  movzx   eax, byte ptr [rdx+1]
0x18000a6b5  or      ecx, eax
0x18000a6b7  add     ecx, 2
0x18000a6ba  cmp     r8d, ecx
0x18000a6bd  jz      short loc_18000A6E6
0x18000a6bf  mov     ebx, 0C0AA02FFh
0x18000a6c4  mov     r9d, ebx
0x18000a6c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6ce  cmp     rcx, r12
0x18000a6d1  jz      short loc_18000A729
0x18000a6d3  test    byte ptr [rcx+1Ch], 4
0x18000a6d7  jz      short loc_18000A729
0x18000a6d9  cmp     byte ptr [rcx+19h], 3
0x18000a6dd  jb      short loc_18000A729
0x18000a6df  mov     edx, 0Bh
0x18000a6e4  jmp     short loc_18000A714
0x18000a6e6  mov     rcx, rbp; this
0x18000a6e9  call    ?Init@CMsftDiscInformation@@AEAAJPEAEJ@Z; CMsftDiscInformation::Init(uchar *,long)
0x18000a6ee  mov     ebx, eax
0x18000a6f0  test    eax, eax
0x18000a6f2  jns     short loc_18000A724
0x18000a6f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6fb  cmp     rcx, r12
0x18000a6fe  jz      short loc_18000A724
0x18000a700  test    byte ptr [rcx+1Ch], 4
0x18000a704  jz      short loc_18000A724
0x18000a706  cmp     byte ptr [rcx+19h], 3
0x18000a70a  jb      short loc_18000A724
0x18000a70c  mov     edx, 0Ch
0x18000a711  mov     r9d, eax
0x18000a714  lea     r8, WPP_7fbbfb794ace3f4195f7fb7939ddc37a_Traceguids
0x18000a71b  mov     rcx, [rcx+10h]
0x18000a71f  call    WPP_SF_d
0x18000a724  mov     rdx, [rsp+38h+pv]
0x18000a729  mov     rcx, rdx; pv
0x18000a72c  call    cs:__imp_CoTaskMemFree
0x18000a732  mov     eax, ebx
0x18000a734  mov     rbx, [rsp+38h+arg_0]
0x18000a739  mov     rbp, [rsp+38h+arg_8]
0x18000a73e  add     rsp, 20h
0x18000a742  pop     r12
0x18000a744  pop     rdi
0x18000a745  pop     rsi
0x18000a746  retn
```
