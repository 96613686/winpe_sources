# NtLmQueryContextAttributes

- ea: `0x140030590`
- end: `0x140030a7f`
- name: `NtLmQueryContextAttributes`
- size: `1263`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140010240`
- `0x1400102c0`
- `0x14002fe40`
- `0x140030590`

## import_xrefs

- `ksecdd!FreeContextBuffer` at `0x1400306d6`
- `ksecdd!FreeContextBuffer` at `0x140030765`
- `ksecdd!FreeContextBuffer` at `0x1400308ad`
- `ksecdd!FreeContextBuffer` at `0x1400306d6`
- `ksecdd!FreeContextBuffer` at `0x140030765`
- `ksecdd!FreeContextBuffer` at `0x1400308ad`
- `ksecdd!KSecAllocateContextBuffer` at `0x140030686`
- `ksecdd!KSecAllocateContextBuffer` at `0x140030721`
- `ksecdd!KSecAllocateContextBuffer` at `0x1400307ca`
- `ksecdd!KSecAllocateContextBuffer` at `0x140030838`
- `ksecdd!KSecAllocateContextBuffer` at `0x14003086b`
- `ksecdd!KSecAllocateContextBuffer` at `0x14003097a`
- `ksecdd!KSecAllocateContextBuffer` at `0x140030686`
- `ksecdd!KSecAllocateContextBuffer` at `0x140030721`
- `ksecdd!KSecAllocateContextBuffer` at `0x1400307ca`
- `ksecdd!KSecAllocateContextBuffer` at `0x140030838`
- `ksecdd!KSecAllocateContextBuffer` at `0x14003086b`
- `ksecdd!KSecAllocateContextBuffer` at `0x14003097a`

## string_xrefs

- `0x1400309d3`: `NTLM Security Package`

## pseudocode

```c
__int64 __fastcall NtLmQueryContextAttributes(char *P, int a2, PVOID *a3)
{
  char *v5; // rbp
  int v6; // edi
  PVOID *v7; // r15
  __int64 v8; // rbx
  bool v9; // cf
  __int64 v10; // rax
  void *v11; // rax
  size_t v12; // rbx
  PVOID v13; // rcx
  __int64 v14; // rax
  void *ContextBuffer; // rax
  const void *v16; // rdx
  size_t v17; // rbx
  unsigned int v19; // ebx
  void *v20; // rax
  unsigned int v21; // eax
  _OWORD *v22; // rax
  PVOID v23; // rcx
  void *v24; // rax
  void *v25; // rax
  __int64 v26; // rdx
  int v27; // eax
  int v28; // ecx
  __int64 v29; // rax
  __int64 v30; // rcx
  _OWORD *v31; // rcx
  int v32; // r14d
  int v33; // r14d
  int v34; // r14d

  v5 = P;
  v6 = (*((__int64 (__fastcall **)(char *, __int64, _QWORD))LsaKernelFunctions + 4))(P, 1296847950, 0);
  if ( v6 < 0 )
  {
    if ( ((a2 - 10) & 0xFFFFFFFD) != 0 )
      return (unsigned int)v6;
    v5 = 0;
    v6 = 0;
  }
  v7 = 0;
  LODWORD(v8) = 0;
  switch ( a2 )
  {
    case 0:
      *(_DWORD *)a3 = 2888;
      *((_DWORD *)a3 + 1) = (*((_DWORD *)v5 + 12) & 0x8030) != 0 ? 0x10 : 0;
      v9 = (*((_DWORD *)v5 + 12) & 0x20) != 0;
      *((_DWORD *)a3 + 2) = v9;
      *((_DWORD *)a3 + 3) = v9 ? 0x10 : 0;
      break;
    case 1:
      if ( a3 )
      {
        v14 = *((_QWORD *)v5 + 16);
        if ( v14 )
        {
          v8 = -1;
          do
            ++v8;
          while ( *(_WORD *)(v14 + 2 * v8) );
        }
        ContextBuffer = (void *)KSecAllocateContextBuffer((unsigned int)(2 * v8 + 2));
        *a3 = ContextBuffer;
        if ( ContextBuffer )
        {
          v16 = (const void *)*((_QWORD *)v5 + 16);
          goto LABEL_22;
        }
        v6 = -1073741670;
        goto LABEL_24;
      }
      v6 = -1073741811;
      break;
    case 3:
      if ( a3 )
      {
        v10 = *((_QWORD *)v5 + 16);
        if ( v10 )
        {
          v8 = -1;
          do
            ++v8;
          while ( *(_WORD *)(v10 + 2 * v8) );
        }
        v11 = (void *)KSecAllocateContextBuffer((unsigned int)(2 * v8 + 2));
        a3[1] = v11;
        if ( v11 )
        {
          v12 = 2LL * (unsigned int)v8;
          memmove(v11, *((const void **)v5 + 16), v12);
          *(_WORD *)((char *)a3[1] + v12) = 0;
          *(_DWORD *)a3 = 0;
        }
        else
        {
          v13 = a3[1];
          v6 = -1073741670;
          if ( v13 )
          {
            FreeContextBuffer(v13);
            a3[1] = 0;
          }
        }
      }
      else
      {
        v6 = -1073741811;
      }
      break;
    case 8:
      v24 = (void *)*((_QWORD *)v5 + 22);
      if ( !v24 )
        goto LABEL_52;
      *a3 = v24;
      break;
    case 9:
      *(_DWORD *)a3 = 16;
      v22 = (_OWORD *)KSecAllocateContextBuffer(16);
      a3[1] = v22;
      if ( !v22 )
      {
        v7 = a3;
        v6 = -1073741670;
        goto LABEL_47;
      }
      *v22 = *(_OWORD *)(v5 + 148);
      break;
    case 10:
    case 12:
      v29 = KSecAllocateContextBuffer(86);
      *a3 = (PVOID)v29;
      if ( !v29 )
      {
        v6 = -1073741670;
        goto LABEL_81;
      }
      *(_QWORD *)(v29 + 16) = v29 + 32;
      *((_QWORD *)*a3 + 3) = *((_QWORD *)*a3 + 2) + 10LL;
      v30 = *((_QWORD *)*a3 + 2);
      *(_QWORD *)v30 = *(_QWORD *)L"NTLM";
      *(_WORD *)(v30 + 8) = aNtlm[4];
      v31 = (_OWORD *)*((_QWORD *)*a3 + 3);
      *v31 = *(_OWORD *)L"NTLM Security Package";
      v31[1] = *(_OWORD *)L"urity Package";
      *(_OWORD *)((char *)v31 + 28) = *(_OWORD *)L"Package";
      *((_WORD *)*a3 + 2) = 1;
      *((_WORD *)*a3 + 3) = 10;
      *(_DWORD *)*a3 = 42478391;
      *((_DWORD *)*a3 + 2) = 2888;
      if ( a2 == 12 )
        *((_DWORD *)a3 + 2) = 0;
      break;
    case 11:
      *(_DWORD *)a3 = *((_DWORD *)v5 + 48);
      break;
    case 14:
      v26 = *((_QWORD *)v5 + 7);
      v27 = 0;
      *(_DWORD *)a3 = 0;
      v28 = *((_DWORD *)v5 + 12);
      if ( (v28 & 0x20) != 0 )
        v27 = 16;
      if ( (v28 & 0x10) != 0 )
      {
        if ( v26 )
          v27 |= 0x2000Cu;
        else
          v27 |= 0x1000Cu;
      }
      if ( (v28 & 0x800) != 0 )
      {
        if ( v26 )
          v27 |= 0x100000u;
        else
          v27 |= 0x40000u;
      }
      if ( (v28 & 0x40) != 0 )
        v27 |= 0x400u;
      if ( (v28 & 0x100000) != 0 )
      {
        if ( v26 )
          v27 |= 0x80000u;
        else
          v27 |= 0x20000u;
      }
      if ( (v28 & 0x4000) != 0 )
        v27 |= 2u;
      *(_DWORD *)a3 = v27;
      break;
    case 17:
      if ( a3 )
      {
        a3[1] = 0;
        if ( *((_QWORD *)v5 + 17) )
        {
          v19 = *((_DWORD *)v5 + 36);
          v20 = (void *)KSecAllocateContextBuffer(v19);
          a3[1] = v20;
          if ( !v20 )
            goto LABEL_35;
          memmove(v20, *((const void **)v5 + 17), v19);
          *(_DWORD *)a3 = v19;
        }
        else
        {
          v6 = -1073741275;
        }
      }
      else
      {
        v6 = -1073741811;
      }
      break;
    case 21:
      v25 = (void *)*((_QWORD *)v5 + 23);
      if ( v25 )
        *a3 = v25;
      else
LABEL_52:
        v6 = -2146893054;
      break;
    case 27:
      if ( a3 )
      {
        if ( *((_QWORD *)v5 + 33)
          && ((LODWORD(v8) = 32766, v21 = *((_DWORD *)v5 + 68) >> 1, v21 > 0x7FFE)
           || (LODWORD(v8) = *((_DWORD *)v5 + 68) >> 1, v21)) )
        {
          ContextBuffer = (void *)KSecAllocateContextBuffer((unsigned int)(2 * v8 + 2));
          *a3 = ContextBuffer;
          if ( ContextBuffer )
          {
            v16 = (const void *)*((_QWORD *)v5 + 33);
LABEL_22:
            v17 = 2LL * (unsigned int)v8;
            memmove(ContextBuffer, v16, v17);
            *(_WORD *)((char *)*a3 + v17) = 0;
          }
          else
          {
LABEL_35:
            v6 = -1073741670;
          }
        }
        else
        {
          v6 = -2146893053;
        }
      }
      else
      {
        v6 = -1073741811;
      }
      break;
    case 37:
      v6 = 0;
      *(_DWORD *)a3 = (*((_DWORD *)v5 + 12) >> 14) & 1;
      break;
    default:
      a3 = 0;
      v6 = -1073741637;
LABEL_81:
      v32 = a2 - 1;
      if ( v32 )
      {
        v33 = v32 - 2;
        if ( v33 )
        {
          v34 = v33 - 6;
          if ( v34 )
          {
            if ( v34 == 3 && a3 )
            {
LABEL_24:
              if ( *a3 )
              {
                FreeContextBuffer(*a3);
                *a3 = 0;
              }
            }
          }
          else
          {
LABEL_47:
            if ( v7 )
            {
              v23 = v7[1];
              if ( v23 )
              {
                FreeContextBuffer(v23);
                v7[1] = 0;
              }
            }
          }
        }
      }
      break;
  }
  if ( v5 )
    NtlmDerefContext(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140030590  push    rbp
0x140030592  push    rsi
0x140030593  push    rdi
0x140030594  push    r14
0x140030596  sub     rsp, 28h
0x14003059a  mov     rax, cs:?LsaKernelFunctions@@3PEAU_SECPKG_KERNEL_FUNCTIONS@@EA; _SECPKG_KERNEL_FUNCTIONS * LsaKernelFunctions
0x1400305a1  mov     rsi, r8
0x1400305a4  mov     r14d, edx
0x1400305a7  xor     r8d, r8d
0x1400305aa  mov     edx, 4D4C544Eh
0x1400305af  mov     rbp, rcx
0x1400305b2  mov     rax, [rax+20h]
0x1400305b6  call    _guard_dispatch_icall
0x1400305bb  xor     r8d, r8d
0x1400305be  mov     edi, eax
0x1400305c0  test    eax, eax
0x1400305c2  jns     short loc_1400305D9
0x1400305c4  lea     eax, [r14-0Ah]
0x1400305c8  test    eax, 0FFFFFFFDh
0x1400305cd  jnz     loc_140030795
0x1400305d3  mov     ebp, r8d
0x1400305d6  mov     edi, r8d
0x1400305d9  mov     [rsp+48h+arg_0], rbx
0x1400305de  mov     [rsp+48h+arg_8], r12
0x1400305e3  mov     [rsp+48h+arg_10], r13
0x1400305e8  mov     [rsp+48h+var_28], r15
0x1400305ed  mov     r15, r8
0x1400305f0  cmp     r14d, 25h; switch 38 cases
0x1400305f4  ja      def_140030617; jumptable 0000000140030617 default case, cases 2,4-7,13,15,16,18-20,22-26,28-36
0x1400305fa  lea     rdx, cs:140000000h
0x140030601  mov     ebx, r8d
0x140030604  movzx   eax, ds:(byte_1400154B8 - 140000000h)[rdx+r14]
0x14003060d  mov     ecx, ds:(jpt_140030617 - 140000000h)[rdx+rax*4]
0x140030614  add     rcx, rdx
0x140030617  jmp     rcx; switch jump
0x14003061d  mov     dword ptr [rsi], 0B48h; jumptable 0000000140030617 case 0
0x140030623  mov     eax, [rbp+30h]
0x140030626  and     eax, 8030h
0x14003062b  neg     eax
0x14003062d  sbb     eax, eax
0x14003062f  and     eax, 10h
0x140030632  mov     [rsi+4], eax
0x140030635  mov     eax, r8d
0x140030638  mov     ecx, [rbp+30h]
0x14003063b  and     ecx, 20h
0x14003063e  setnz   al
0x140030641  neg     ecx
0x140030643  mov     [rsi+8], eax
0x140030646  sbb     eax, eax
0x140030648  and     eax, 10h
0x14003064b  mov     [rsi+0Ch], eax
0x14003064e  jmp     loc_140030774
0x140030653  test    rsi, rsi; jumptable 0000000140030617 case 3
0x140030656  jnz     short loc_140030662
0x140030658  mov     edi, 0C000000Dh
0x14003065d  jmp     loc_140030774
0x140030662  mov     rax, [rbp+80h]
0x140030669  test    rax, rax
0x14003066c  jz      short loc_14003067F
0x14003066e  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x140030675  inc     rbx
0x140030678  cmp     [rax+rbx*2], r8w
0x14003067d  jnz     short loc_140030675
0x14003067f  lea     ecx, ds:2[rbx*2]
0x140030686  call    cs:__imp_KSecAllocateContextBuffer
0x14003068d  nop     dword ptr [rax+rax+00h]
0x140030692  mov     [rsi+8], rax
0x140030696  test    rax, rax
0x140030699  jz      short loc_1400306C4
0x14003069b  mov     rdx, [rbp+80h]; Src
0x1400306a2  mov     ecx, ebx
0x1400306a4  lea     rbx, [rcx+rcx]
0x1400306a8  mov     rcx, rax; void *
0x1400306ab  mov     r8, rbx; Size
0x1400306ae  call    memmove
0x1400306b3  mov     rcx, [rsi+8]
0x1400306b7  xor     eax, eax
0x1400306b9  mov     [rbx+rcx], ax
0x1400306bd  mov     [rsi], eax
0x1400306bf  jmp     loc_140030774
0x1400306c4  mov     rcx, [rsi+8]; pvContextBuffer
0x1400306c8  mov     edi, 0C000009Ah
0x1400306cd  test    rcx, rcx
0x1400306d0  jz      loc_140030774
0x1400306d6  call    cs:__imp_FreeContextBuffer
0x1400306dd  nop     dword ptr [rax+rax+00h]
0x1400306e2  mov     [rsi+8], r15
0x1400306e6  jmp     loc_140030774
0x1400306eb  test    rsi, rsi; jumptable 0000000140030617 case 1
0x1400306ee  jnz     short loc_1400306FA
0x1400306f0  mov     edi, 0C000000Dh
0x1400306f5  jmp     loc_140030774
0x1400306fa  mov     rax, [rbp+80h]
0x140030701  test    rax, rax
0x140030704  jz      short loc_14003071A
0x140030706  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x14003070d  nop     dword ptr [rax]
0x140030710  inc     rbx
0x140030713  cmp     [rax+rbx*2], r8w
0x140030718  jnz     short loc_140030710
0x14003071a  lea     ecx, ds:2[rbx*2]
0x140030721  call    cs:__imp_KSecAllocateContextBuffer
0x140030728  nop     dword ptr [rax+rax+00h]
0x14003072d  mov     [rsi], rax
0x140030730  test    rax, rax
0x140030733  jz      short loc_140030758
0x140030735  mov     rdx, [rbp+80h]; Src
0x14003073c  mov     ecx, ebx
0x14003073e  lea     rbx, [rcx+rcx]
0x140030742  mov     rcx, rax; void *
0x140030745  mov     r8, rbx; Size
0x140030748  call    memmove
0x14003074d  mov     rcx, [rsi]
0x140030750  xor     eax, eax
0x140030752  mov     [rbx+rcx], ax
0x140030756  jmp     short loc_140030774
0x140030758  mov     edi, 0C000009Ah
0x14003075d  mov     rcx, [rsi]; pvContextBuffer
0x140030760  test    rcx, rcx
0x140030763  jz      short loc_140030774
0x140030765  call    cs:__imp_FreeContextBuffer
0x14003076c  nop     dword ptr [rax+rax+00h]
0x140030771  mov     [rsi], r15
0x140030774  mov     r15, [rsp+48h+var_28]
0x140030779  mov     r13, [rsp+48h+arg_10]
0x14003077e  mov     r12, [rsp+48h+arg_8]
0x140030783  mov     rbx, [rsp+48h+arg_0]
0x140030788  test    rbp, rbp
0x14003078b  jz      short loc_140030795
0x14003078d  mov     rcx, rbp; P
0x140030790  call    NtlmDerefContext
0x140030795  mov     eax, edi
0x140030797  add     rsp, 28h
0x14003079b  pop     r14
0x14003079d  pop     rdi
0x14003079e  pop     rsi
0x14003079f  pop     rbp
0x1400307a0  retn
0x1400307a2  test    rsi, rsi; jumptable 0000000140030617 case 17
0x1400307a5  jnz     short loc_1400307AE
0x1400307a7  mov     edi, 0C000000Dh
0x1400307ac  jmp     short loc_140030774
0x1400307ae  mov     [rsi+8], r8
0x1400307b2  cmp     [rbp+88h], rbx
0x1400307b9  jnz     short loc_1400307C2
0x1400307bb  mov     edi, 0C0000225h
0x1400307c0  jmp     short loc_140030774
0x1400307c2  mov     ebx, [rbp+90h]
0x1400307c8  mov     ecx, ebx
0x1400307ca  call    cs:__imp_KSecAllocateContextBuffer
0x1400307d1  nop     dword ptr [rax+rax+00h]
0x1400307d6  mov     [rsi+8], rax
0x1400307da  test    rax, rax
0x1400307dd  jz      short loc_1400307F8
0x1400307df  mov     rdx, [rbp+88h]; Src
0x1400307e6  mov     r8d, ebx; Size
0x1400307e9  mov     rcx, rax; void *
0x1400307ec  call    memmove
0x1400307f1  mov     [rsi], ebx
0x1400307f3  jmp     loc_140030774
0x1400307f8  mov     edi, 0C000009Ah
0x1400307fd  jmp     loc_140030774
0x140030802  test    rsi, rsi; jumptable 0000000140030617 case 27
0x140030805  jnz     short loc_140030811
0x140030807  mov     edi, 0C000000Dh
0x14003080c  jmp     loc_140030774
0x140030811  cmp     [rbp+108h], rbx
0x140030818  jz      short loc_140030858
0x14003081a  mov     eax, [rbp+110h]
0x140030820  mov     ebx, 7FFEh
0x140030825  shr     eax, 1
0x140030827  cmp     eax, ebx
0x140030829  ja      short loc_140030831
0x14003082b  mov     ebx, eax
0x14003082d  test    eax, eax
0x14003082f  jz      short loc_140030858
0x140030831  lea     ecx, ds:2[rbx*2]
0x140030838  call    cs:__imp_KSecAllocateContextBuffer
0x14003083f  nop     dword ptr [rax+rax+00h]
0x140030844  mov     [rsi], rax
0x140030847  test    rax, rax
0x14003084a  jz      short loc_1400307F8
0x14003084c  mov     rdx, [rbp+108h]
0x140030853  jmp     loc_14003073C
0x140030858  mov     edi, 80090303h
0x14003085d  jmp     loc_140030774
0x140030862  mov     eax, 10h; jumptable 0000000140030617 case 9
0x140030867  mov     [rsi], eax
0x140030869  mov     ecx, eax
0x14003086b  call    cs:__imp_KSecAllocateContextBuffer
0x140030872  nop     dword ptr [rax+rax+00h]
0x140030877  mov     [rsi+8], rax
0x14003087b  test    rax, rax
0x14003087e  jz      short loc_14003088F
0x140030880  movups  xmm0, xmmword ptr [rbp+94h]
0x140030887  movups  xmmword ptr [rax], xmm0
0x14003088a  jmp     loc_140030774
0x14003088f  mov     r15, rsi
0x140030892  mov     edi, 0C000009Ah
0x140030897  test    r15, r15
0x14003089a  jz      loc_140030774
0x1400308a0  mov     rcx, [r15+8]; pvContextBuffer
0x1400308a4  test    rcx, rcx
0x1400308a7  jz      loc_140030774
0x1400308ad  call    cs:__imp_FreeContextBuffer
0x1400308b4  nop     dword ptr [rax+rax+00h]
0x1400308b9  mov     qword ptr [r15+8], 0
0x1400308c1  jmp     loc_140030774
0x1400308c6  mov     rax, [rbp+0B0h]; jumptable 0000000140030617 case 8
0x1400308cd  test    rax, rax
0x1400308d0  jz      short loc_1400308DA
0x1400308d2  mov     [rsi], rax
0x1400308d5  jmp     loc_140030774
0x1400308da  mov     edi, 80090302h
0x1400308df  jmp     loc_140030774
0x1400308e4  mov     rax, [rbp+0B8h]; jumptable 0000000140030617 case 21
0x1400308eb  test    rax, rax
0x1400308ee  jz      short loc_1400308DA
0x1400308f0  mov     [rsi], rax
0x1400308f3  jmp     loc_140030774
0x1400308f8  mov     eax, [rbp+0C0h]; jumptable 0000000140030617 case 11
0x1400308fe  mov     [rsi], eax
0x140030900  jmp     loc_140030774
0x140030905  mov     rdx, [rbp+38h]; jumptable 0000000140030617 case 14
0x140030909  mov     eax, r8d
0x14003090c  mov     [rsi], r8d
0x14003090f  mov     ecx, [rbp+30h]
0x140030912  test    cl, 20h
0x140030915  jz      short loc_14003091C
0x140030917  mov     eax, 10h
0x14003091c  test    cl, 10h
0x14003091f  jz      short loc_140030932
0x140030921  test    rdx, rdx
0x140030924  jnz     short loc_14003092D
0x140030926  or      eax, 1000Ch
0x14003092b  jmp     short loc_140030932
0x14003092d  or      eax, 2000Ch
0x140030932  bt      ecx, 0Bh
0x140030936  jnb     short loc_140030947
0x140030938  test    rdx, rdx
0x14003093b  jnz     short loc_140030943
0x14003093d  bts     eax, 12h
0x140030941  jmp     short loc_140030947
0x140030943  bts     eax, 14h
0x140030947  test    cl, 40h
0x14003094a  jz      short loc_140030950
0x14003094c  bts     eax, 0Ah
0x140030950  bt      ecx, 14h
0x140030954  jnb     short loc_140030965
0x140030956  test    rdx, rdx
0x140030959  jnz     short loc_140030961
0x14003095b  bts     eax, 11h
0x14003095f  jmp     short loc_140030965
0x140030961  bts     eax, 13h
0x140030965  bt      ecx, 0Eh
0x140030969  jnb     short loc_14003096E
0x14003096b  or      eax, 2
0x14003096e  mov     [rsi], eax
0x140030970  jmp     loc_140030774
0x140030975  mov     ecx, 56h ; 'V'; jumptable 0000000140030617 cases 10,12
0x14003097a  call    cs:__imp_KSecAllocateContextBuffer
0x140030981  nop     dword ptr [rax+rax+00h]
0x140030986  mov     [rsi], rax
0x140030989  mov     rcx, rax
0x14003098c  test    rax, rax
0x14003098f  jnz     short loc_14003099B
0x140030991  mov     edi, 0C000009Ah
0x140030996  jmp     loc_140030A49
0x14003099b  add     rax, 20h ; ' '
0x14003099f  mov     [rcx+10h], rax
0x1400309a3  mov     rcx, [rsi]
0x1400309a6  mov     rax, [rcx+10h]
0x1400309aa  add     rax, 0Ah
0x1400309ae  mov     [rcx+18h], rax
0x1400309b2  mov     rax, [rsi]
0x1400309b5  movsd   xmm0, qword ptr cs:aNtlm; "NTLM"
0x1400309bd  mov     rcx, [rax+10h]
0x1400309c1  movsd   qword ptr [rcx], xmm0
0x1400309c5  movzx   eax, word ptr cs:aNtlm+8; ""
0x1400309cc  mov     [rcx+8], ax
0x1400309d0  mov     rax, [rsi]
0x1400309d3  movups  xmm0, xmmword ptr cs:aNtlmSecurityPa; "NTLM Security Package"
0x1400309da  mov     rcx, [rax+18h]
0x1400309de  movups  xmmword ptr [rcx], xmm0
0x1400309e1  movups  xmm1, xmmword ptr cs:aNtlmSecurityPa+10h; "urity Package"
0x1400309e8  movups  xmmword ptr [rcx+10h], xmm1
0x1400309ec  movups  xmm0, xmmword ptr cs:aNtlmSecurityPa+1Ch; "Package"
0x1400309f3  movups  xmmword ptr [rcx+1Ch], xmm0
0x1400309f7  mov     rax, [rsi]
0x1400309fa  mov     word ptr [rax+4], 1
0x140030a00  mov     rax, [rsi]
0x140030a03  mov     word ptr [rax+6], 0Ah
0x140030a09  mov     rax, [rsi]
0x140030a0c  mov     dword ptr [rax], 2882B37h
0x140030a12  mov     rax, [rsi]
0x140030a15  mov     dword ptr [rax+8], 0B48h
0x140030a1c  cmp     r14d, 0Ch
0x140030a20  jnz     loc_140030774
0x140030a26  mov     [rsi+8], ebx
0x140030a29  jmp     loc_140030774
  ... truncated ...
```
