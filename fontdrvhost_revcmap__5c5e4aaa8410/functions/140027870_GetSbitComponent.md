# GetSbitComponent

- ea: `0x140027870`
- end: `0x140027ced`
- name: `GetSbitComponent`
- size: `1149`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int, __int16, __int16, __int16, __int16, __int16, __int16, __int16, __int16, __int16, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140027224`
- `0x140027870`

## callees

- `0x140016e40`
- `0x1400265a8`
- `0x140026c04`
- `0x140027870`
- `0x14002859c`
- `0x140028af0`
- `0x140072578`
- `0x140098010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetSbitComponent(
        const struct sfac_ClientRec *a1,
        int a2,
        unsigned __int16 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int16 a6,
        unsigned __int16 a7,
        unsigned __int16 a8,
        unsigned __int16 a9,
        unsigned __int16 a10,
        unsigned __int16 a11,
        unsigned __int16 a12,
        unsigned __int16 a13,
        __int16 a14,
        unsigned int a15,
        unsigned __int8 *a16)
{
  unsigned int v16; // r14d
  unsigned int v17; // ebx
  unsigned __int16 v19; // si
  __int64 result; // rax
  unsigned __int16 v21; // r14
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // rdx
  unsigned __int8 *v27; // rdx
  unsigned int v28; // ebx
  __int16 v29; // ax
  __int16 v30; // cx
  __int64 v31; // rdx
  __int64 v32; // rcx
  unsigned int v33; // r10d
  unsigned int v34; // r8d
  __int16 v35; // [rsp+68h] [rbp-89h]
  bool v36; // [rsp+88h] [rbp-69h] BYREF
  unsigned __int16 v37; // [rsp+8Ch] [rbp-65h] BYREF
  __int16 v38[2]; // [rsp+90h] [rbp-61h] BYREF
  __int16 v39; // [rsp+94h] [rbp-5Dh] BYREF
  __int16 v40[2]; // [rsp+98h] [rbp-59h] BYREF
  __int16 v41; // [rsp+9Ch] [rbp-55h] BYREF
  unsigned __int16 v42[2]; // [rsp+A0h] [rbp-51h] BYREF
  unsigned __int16 v43; // [rsp+A4h] [rbp-4Dh] BYREF
  unsigned __int16 v44[2]; // [rsp+A8h] [rbp-49h] BYREF
  unsigned __int16 v45; // [rsp+ACh] [rbp-45h] BYREF
  unsigned __int16 v46[2]; // [rsp+B0h] [rbp-41h] BYREF
  unsigned __int16 v47; // [rsp+B4h] [rbp-3Dh] BYREF
  unsigned __int16 v48[2]; // [rsp+B8h] [rbp-39h] BYREF
  unsigned __int16 v49; // [rsp+BCh] [rbp-35h] BYREF
  unsigned __int16 v50[2]; // [rsp+C0h] [rbp-31h] BYREF
  unsigned __int16 v51; // [rsp+C4h] [rbp-2Dh] BYREF
  unsigned __int16 v52[2]; // [rsp+C8h] [rbp-29h] BYREF
  unsigned __int16 v53; // [rsp+CCh] [rbp-25h] BYREF
  unsigned int v54; // [rsp+D0h] [rbp-21h] BYREF
  unsigned int v55; // [rsp+D4h] [rbp-1Dh] BYREF
  unsigned int v56; // [rsp+D8h] [rbp-19h] BYREF
  __int64 v57; // [rsp+E0h] [rbp-11h] BYREF
  _QWORD v58[2]; // [rsp+E8h] [rbp-9h] BYREF

  v16 = a4;
  v17 = a2;
  v19 = 0;
  v56 = 0;
  v55 = 0;
  v54 = 0;
  v37 = 0;
  v43 = 0;
  v48[0] = 0;
  v46[0] = 0;
  v44[0] = 0;
  v45 = 0;
  v42[0] = 0;
  v49 = 0;
  v50[0] = 0;
  v47 = 0;
  v41 = 0;
  v40[0] = 0;
  v39 = 0;
  v38[0] = 0;
  v36 = 0;
  result = sfac_GetSbitBitmap(a1, a3, a4, a5, a6, a7, a8, a9, a10, a11, a12, a14, a15, a16, &v37);
  if ( !(_DWORD)result )
  {
    if ( !v37 )
      return 0;
    if ( (unsigned int)a13 + 1 > 0x14 )
      return 5131;
    while ( 1 )
    {
      if ( v37 <= v19 )
        return 0;
      result = sfac_GetSbitComponentInfo(a1, v19, v16, a5, &v43, v48, v46);
      if ( (_DWORD)result )
        return result;
      result = sfac_SearchForBitmap(a1, v43, v17, &v36, v44, &v45, &v56, v42, &v55, &v54);
      if ( (_DWORD)result )
        return result;
      if ( !v36 )
        return 6145;
      v21 = v44[0];
      if ( v45 == 2 )
      {
        v22 = 164;
        v23 = 160;
      }
      else
      {
        v22 = 172;
        v23 = 168;
      }
      v24 = 8;
      if ( v44[0] != 3 )
        v24 = 5;
      v25 = 0;
      v57 = 0;
      if ( *(_DWORD *)((char *)a1 + v22) )
      {
        v26 = v56 + *(_DWORD *)((char *)a1 + v23);
        if ( (unsigned int)v26 > 0x7FFFFFFF || (unsigned int)v26 < v56 )
        {
          v29 = SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(0, v26);
LABEL_37:
          v39 = v29;
          v38[0] = v30;
          goto LABEL_21;
        }
        v27 = (unsigned __int8 *)(*((__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64 *))a1 + 1))(
                                   *(_QWORD *)a1,
                                   v26,
                                   v24,
                                   &v57);
        v28 = v27 == 0 ? 0x1408 : 0;
        v25 = v57;
      }
      else
      {
        v27 = 0;
        v28 = 5129;
      }
      v58[0] = a1;
      v58[1] = v25;
      if ( v28 )
      {
        if ( v25 )
          (*((void (__fastcall **)(__int64, unsigned __int8 *))a1 + 2))(v25, v27);
        return v28;
      }
      v52[0] = *v27;
      v51 = v27[1];
      v29 = (char)v27[2];
      v30 = (char)v27[3];
      LOWORD(v17) = 1;
      if ( v21 == 3 )
      {
        v41 = (char)v27[2];
        v40[0] = v30;
        v39 = (char)v27[5];
        v38[0] = (char)v27[6];
      }
      else
      {
        if ( v21 != 1 )
          goto LABEL_37;
        v41 = (char)v27[2];
        v40[0] = v30;
      }
LABEL_21:
      AutoReleaseSfntFrag::~AutoReleaseSfntFrag((AutoReleaseSfntFrag *)v58);
      v53 = 0;
      result = sfac_ShaveSbitMetrics(a1, v42[0], v55, v54, v52, &v51, &v49, v50, &v47, &v53, &v41, v40, &v39, v38);
      if ( (_DWORD)result )
        return result;
      v31 = v46[0];
      v32 = v46[0] + (unsigned int)a12;
      if ( (unsigned int)v32 > 0xFFFF )
        goto LABEL_39;
      LOWORD(v31) = a12 + v46[0];
      v33 = v47 + (unsigned __int16)(a12 + v46[0]);
      if ( v33 > 0xFFFF )
        goto LABEL_39;
      v31 = v48[0];
      v32 = v48[0] + (unsigned int)a11;
      if ( (unsigned int)v32 > 0xFFFF )
        goto LABEL_39;
      v31 = v49;
      v34 = v49 + (unsigned __int16)(a11 + v48[0]);
      if ( v34 > 0xFFFF )
        goto LABEL_39;
      v35 = v17 + a13;
      v17 = a2;
      result = GetSbitComponent(
                 (int)a1,
                 a2,
                 v42[0],
                 v55,
                 v54,
                 v52[0],
                 v51,
                 v49,
                 v50[0],
                 v47,
                 v34,
                 v33,
                 v35,
                 a14,
                 a15,
                 a16);
      if ( (_DWORD)result )
        return result;
      if ( v19 == 0xFFFF )
      {
LABEL_39:
        SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v32, v31);
        __debugbreak();
      }
      ++v19;
      v16 = a4;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140027870  mov     rax, rsp
0x140027873  mov     [rax+8], rbx
0x140027877  mov     [rax+18h], rsi
0x14002787b  mov     [rax+20h], r9d
0x14002787f  mov     [rax+10h], edx
0x140027882  push    rbp
0x140027883  push    rdi
0x140027884  push    r12
0x140027886  push    r13
0x140027888  push    r14
0x14002788a  lea     rbp, [rax-2Fh]
0x14002788e  sub     rsp, 0F0h
0x140027895  mov     r14d, r9d
0x140027898  movzx   r10d, r8w
0x14002789c  mov     ebx, edx
0x14002789e  mov     rdi, rcx
0x1400278a1  xor     esi, esi
0x1400278a3  mov     [rbp+27h+var_40], esi
0x1400278a6  mov     [rbp+27h+var_44], esi
0x1400278a9  mov     [rbp+27h+var_48], esi
0x1400278ac  mov     [rbp+27h+var_8C], si
0x1400278b0  mov     [rbp+27h+var_74], si
0x1400278b4  mov     [rbp+27h+var_60], si
0x1400278b8  mov     [rbp+27h+var_68], si
0x1400278bc  mov     [rbp+27h+var_70], si
0x1400278c0  mov     [rbp+27h+var_6C], si
0x1400278c4  mov     [rbp+27h+var_78], si
0x1400278c8  mov     [rbp+27h+var_5C], si
0x1400278cc  mov     [rbp+27h+var_58], si
0x1400278d0  mov     [rbp+27h+var_64], si
0x1400278d4  mov     [rbp+27h+var_7C], si
0x1400278d8  mov     [rbp+27h+var_80], si
0x1400278dc  mov     [rbp+27h+var_84], si
0x1400278e0  mov     [rbp+27h+var_88], si
0x1400278e4  mov     [rbp+27h+var_90], sil
0x1400278e8  lea     rax, [rbp+27h+var_8C]
0x1400278ec  mov     [rsp+110h+var_A0], rax; unsigned __int16 *
0x1400278f1  mov     rax, [rbp+27h+arg_78]
0x1400278f8  mov     [rsp+110h+var_A8], rax; unsigned __int8 *
0x1400278fd  mov     eax, [rbp+27h+arg_70]
0x140027903  mov     dword ptr [rsp+110h+var_B0], eax; unsigned int
0x140027907  movzx   eax, [rbp+27h+arg_68]
0x14002790e  mov     word ptr [rsp+110h+var_B8], ax; unsigned __int16
0x140027913  movzx   r12d, [rbp+27h+arg_58]
0x14002791b  mov     word ptr [rsp+110h+var_C0], r12w; unsigned __int16
0x140027921  movzx   r13d, [rbp+27h+arg_50]
0x140027929  mov     word ptr [rsp+110h+var_C8], r13w; unsigned __int16
0x14002792f  movzx   eax, [rbp+27h+arg_48]
0x140027933  mov     word ptr [rsp+110h+var_D0], ax; unsigned __int16
0x140027938  movzx   eax, [rbp+27h+arg_40]
0x14002793c  mov     word ptr [rsp+110h+var_D8], ax; unsigned __int16
0x140027941  movzx   eax, [rbp+27h+arg_38]
0x140027945  mov     word ptr [rsp+110h+var_E0], ax; unsigned __int16
0x14002794a  movzx   eax, [rbp+27h+arg_30]
0x14002794e  mov     word ptr [rsp+110h+var_E8], ax; unsigned __int16
0x140027953  movzx   eax, [rbp+27h+arg_28]
0x140027957  mov     word ptr [rsp+110h+var_F0], ax; unsigned __int16
0x14002795c  mov     r9d, [rbp+27h+arg_20]; unsigned int
0x140027960  mov     r8d, r14d; unsigned int
0x140027963  movzx   edx, r10w; unsigned __int16
0x140027967  call    ?sfac_GetSbitBitmap@@YAHPEBUsfac_ClientRec@@GIIGGGGGGGGIPEAEPEAG@Z; sfac_GetSbitBitmap(sfac_ClientRec const *,ushort,uint,uint,ushort,ushort,ushort,ushort,ushort,ushort,ushort,ushort,uint,uchar *,ushort *)
0x14002796c  test    eax, eax
0x14002796e  jnz     short loc_140027978
0x140027970  cmp     [rbp+27h+var_8C], si
0x140027974  ja      short loc_140027994
0x140027976  xor     eax, eax
0x140027978  lea     r11, [rsp+110h+var_20]
0x140027980  mov     rbx, [r11+30h]
0x140027984  mov     rsi, [r11+40h]
0x140027988  mov     rsp, r11
0x14002798b  pop     r14
0x14002798d  pop     r13
0x14002798f  pop     r12
0x140027991  pop     rdi
0x140027992  pop     rbp
0x140027993  retn
0x140027994  movzx   eax, [rbp+27h+arg_60]
0x14002799b  inc     eax
0x14002799d  cmp     eax, 14h
0x1400279a0  ja      loc_140027CD3
0x1400279a6  cmp     [rbp+27h+var_8C], si
0x1400279aa  jbe     short loc_140027976
0x1400279ac  lea     rax, [rbp+27h+var_68]
0x1400279b0  mov     [rsp+110h+var_E0], rax; unsigned __int16 *
0x1400279b5  lea     rax, [rbp+27h+var_60]
0x1400279b9  mov     [rsp+110h+var_E8], rax; unsigned __int16 *
0x1400279be  lea     rax, [rbp+27h+var_74]
0x1400279c2  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x1400279c7  mov     r9d, [rbp+27h+arg_20]; unsigned int
0x1400279cb  mov     r8d, r14d; unsigned int
0x1400279ce  movzx   edx, si; unsigned __int16
0x1400279d1  mov     rcx, rdi; struct sfac_ClientRec *
0x1400279d4  call    ?sfac_GetSbitComponentInfo@@YAHPEBUsfac_ClientRec@@GIIPEAG11@Z; sfac_GetSbitComponentInfo(sfac_ClientRec const *,ushort,uint,uint,ushort *,ushort *,ushort *)
0x1400279d9  test    eax, eax
0x1400279db  jnz     short loc_140027978
0x1400279dd  lea     rax, [rbp+27h+var_48]
0x1400279e1  mov     [rsp+110h+var_C8], rax; unsigned int *
0x1400279e6  lea     rax, [rbp+27h+var_44]
0x1400279ea  mov     [rsp+110h+var_D0], rax; unsigned int *
0x1400279ef  lea     rax, [rbp+27h+var_78]
0x1400279f3  mov     [rsp+110h+var_D8], rax; unsigned __int16 *
0x1400279f8  lea     rax, [rbp+27h+var_40]
0x1400279fc  mov     [rsp+110h+var_E0], rax; unsigned int *
0x140027a01  lea     rax, [rbp+27h+var_6C]
0x140027a05  mov     [rsp+110h+var_E8], rax; unsigned __int16 *
0x140027a0a  lea     rax, [rbp+27h+var_70]
0x140027a0e  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x140027a13  lea     r9, [rbp+27h+var_90]; bool *
0x140027a17  mov     r8d, ebx; unsigned int
0x140027a1a  movzx   edx, [rbp+27h+var_74]; unsigned __int16
0x140027a1e  mov     rcx, rdi; struct sfac_ClientRec *
0x140027a21  call    ?sfac_SearchForBitmap@@YAHPEBUsfac_ClientRec@@GIPEA_NPEAG2PEAI233@Z; sfac_SearchForBitmap(sfac_ClientRec const *,ushort,uint,bool *,ushort *,ushort *,uint *,ushort *,uint *,uint *)
0x140027a26  test    eax, eax
0x140027a28  jnz     loc_140027978
0x140027a2e  cmp     [rbp+27h+var_90], al
0x140027a31  jz      loc_140027CE3
0x140027a37  movzx   r14d, [rbp+27h+var_70]
0x140027a3c  cmp     [rbp+27h+var_6C], 2
0x140027a41  jnz     loc_140027C7D
0x140027a47  mov     eax, 0A4h
0x140027a4c  lea     edx, [rax-4]
0x140027a4f  mov     ecx, 5
0x140027a54  lea     r8d, [rcx+3]
0x140027a58  cmp     r14w, 3
0x140027a5d  cmovnz  r8d, ecx
0x140027a61  xor     ecx, ecx
0x140027a63  mov     [rbp+27h+var_38], rcx
0x140027a67  cmp     [rax+rdi], ecx
0x140027a6a  jbe     loc_140027C8A
0x140027a70  mov     edx, [rdx+rdi]
0x140027a73  add     edx, [rbp+27h+var_40]
0x140027a76  cmp     edx, 7FFFFFFFh
0x140027a7c  ja      loc_140027CB5
0x140027a82  cmp     edx, [rbp+27h+var_40]
0x140027a85  jb      loc_140027CB5
0x140027a8b  lea     r9, [rbp+27h+var_38]
0x140027a8f  mov     rcx, [rdi]
0x140027a92  mov     rax, [rdi+8]
0x140027a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027a9b  mov     rdx, rax
0x140027a9e  mov     rcx, rax
0x140027aa1  neg     rcx
0x140027aa4  sbb     ebx, ebx
0x140027aa6  not     ebx
0x140027aa8  and     ebx, 1408h
0x140027aae  mov     rcx, [rbp+27h+var_38]
0x140027ab2  mov     [rbp+27h+var_30], rdi
0x140027ab6  mov     [rbp+27h+var_28], rcx
0x140027aba  test    ebx, ebx
0x140027abc  jnz     loc_140027C96
0x140027ac2  movzx   eax, byte ptr [rdx]
0x140027ac5  mov     [rbp+27h+var_50], ax
0x140027ac9  movzx   eax, byte ptr [rdx+1]
0x140027acd  mov     [rbp+27h+var_54], ax
0x140027ad1  movsx   eax, byte ptr [rdx+2]
0x140027ad5  movsx   ecx, byte ptr [rdx+3]
0x140027ad9  mov     ebx, 1
0x140027ade  cmp     r14w, 3
0x140027ae3  jnz     loc_140027CA2
0x140027ae9  mov     [rbp+27h+var_7C], ax
0x140027aed  mov     [rbp+27h+var_80], cx
0x140027af1  movsx   eax, byte ptr [rdx+5]
0x140027af5  mov     [rbp+27h+var_84], ax
0x140027af9  movsx   eax, byte ptr [rdx+6]
0x140027afd  mov     [rbp+27h+var_88], ax
0x140027b01  lea     rcx, [rbp+27h+var_30]; this
0x140027b05  call    ??1AutoReleaseSfntFrag@@QEAA@XZ; AutoReleaseSfntFrag::~AutoReleaseSfntFrag(void)
0x140027b0a  xor     eax, eax
0x140027b0c  mov     [rbp+27h+var_4C], ax
0x140027b10  lea     rax, [rbp+27h+var_88]
0x140027b14  mov     [rsp+110h+var_A8], rax; __int16 *
0x140027b19  lea     rax, [rbp+27h+var_84]
0x140027b1d  mov     [rsp+110h+var_B0], rax; __int16 *
0x140027b22  lea     rax, [rbp+27h+var_80]
0x140027b26  mov     [rsp+110h+var_B8], rax; __int16 *
0x140027b2b  lea     rax, [rbp+27h+var_7C]
0x140027b2f  mov     [rsp+110h+var_C0], rax; __int16 *
0x140027b34  lea     rax, [rbp+27h+var_4C]
0x140027b38  mov     [rsp+110h+var_C8], rax; unsigned __int16 *
0x140027b3d  lea     rax, [rbp+27h+var_64]
0x140027b41  mov     [rsp+110h+var_D0], rax; unsigned __int16 *
0x140027b46  lea     rax, [rbp+27h+var_58]
0x140027b4a  mov     [rsp+110h+var_D8], rax; unsigned __int16 *
0x140027b4f  lea     rax, [rbp+27h+var_5C]
0x140027b53  mov     [rsp+110h+var_E0], rax; unsigned __int16 *
0x140027b58  lea     rax, [rbp+27h+var_54]
0x140027b5c  mov     [rsp+110h+var_E8], rax; unsigned __int16 *
0x140027b61  lea     rax, [rbp+27h+var_50]
0x140027b65  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x140027b6a  mov     r9d, [rbp+27h+var_48]; unsigned int
0x140027b6e  mov     r8d, [rbp+27h+var_44]; unsigned int
0x140027b72  movzx   edx, [rbp+27h+var_78]; unsigned __int16
0x140027b76  mov     rcx, rdi; struct sfac_ClientRec *
0x140027b79  call    ?sfac_ShaveSbitMetrics@@YAHPEBUsfac_ClientRec@@GIIPEAG11111PEAF222@Z; sfac_ShaveSbitMetrics(sfac_ClientRec const *,ushort,uint,uint,ushort *,ushort *,ushort *,ushort *,ushort *,ushort *,short *,short *,short *,short *)
0x140027b7e  test    eax, eax
0x140027b80  jnz     loc_140027978
0x140027b86  movzx   edx, [rbp+27h+var_68]
0x140027b8a  lea     ecx, [rdx+r12]
0x140027b8e  mov     r14d, 0FFFFh
0x140027b94  cmp     ecx, r14d
0x140027b97  ja      loc_140027CDD
0x140027b9d  add     dx, r12w
0x140027ba1  movzx   r10d, dx
0x140027ba5  movzx   r9d, [rbp+27h+var_64]
0x140027baa  add     r10d, r9d
0x140027bad  cmp     r10d, r14d
0x140027bb0  ja      loc_140027CDD
0x140027bb6  movzx   edx, [rbp+27h+var_60]
0x140027bba  lea     ecx, [rdx+r13]
0x140027bbe  cmp     ecx, r14d
0x140027bc1  ja      loc_140027CDD
0x140027bc7  add     dx, r13w
0x140027bcb  movzx   r8d, dx
0x140027bcf  movzx   edx, [rbp+27h+var_5C]
0x140027bd3  add     r8d, edx
0x140027bd6  cmp     r8d, r14d
0x140027bd9  ja      loc_140027CDD
0x140027bdf  mov     ecx, [rbp+27h+var_48]
0x140027be2  movzx   eax, [rbp+27h+arg_60]
0x140027be9  add     ax, bx
0x140027bec  mov     r11, [rbp+27h+arg_78]
0x140027bf3  mov     [rsp+110h+var_98], r11; unsigned __int8 *
0x140027bf8  mov     r11d, [rbp+27h+arg_70]
0x140027bff  mov     dword ptr [rsp+110h+var_A0], r11d; unsigned int
0x140027c04  movzx   r11d, [rbp+27h+arg_68]
0x140027c0c  mov     word ptr [rsp+110h+var_A8], r11w; __int16
0x140027c12  mov     word ptr [rsp+110h+var_B0], ax; __int16
0x140027c17  mov     word ptr [rsp+110h+var_B8], r10w; __int16
0x140027c1d  mov     word ptr [rsp+110h+var_C0], r8w; __int16
0x140027c23  mov     word ptr [rsp+110h+var_C8], r9w; __int16
0x140027c29  movzx   eax, [rbp+27h+var_58]
0x140027c2d  mov     word ptr [rsp+110h+var_D0], ax; __int16
0x140027c32  mov     word ptr [rsp+110h+var_D8], dx; __int16
0x140027c37  movzx   eax, [rbp+27h+var_54]
0x140027c3b  mov     word ptr [rsp+110h+var_E0], ax; __int16
0x140027c40  movzx   eax, [rbp+27h+var_50]
0x140027c44  mov     word ptr [rsp+110h+var_E8], ax; __int16
0x140027c49  mov     dword ptr [rsp+110h+var_F0], ecx; unsigned int
0x140027c4d  mov     r9d, [rbp+27h+var_44]; int
0x140027c51  movzx   r8d, [rbp+27h+var_78]; int
0x140027c56  mov     ebx, [rbp+27h+arg_8]
0x140027c59  mov     edx, ebx; int
0x140027c5b  mov     rcx, rdi; int
0x140027c5e  call    GetSbitComponent
0x140027c63  test    eax, eax
0x140027c65  jnz     loc_140027978
0x140027c6b  cmp     si, r14w
0x140027c6f  jz      short loc_140027CDD
0x140027c71  inc     si
0x140027c74  mov     r14d, [rbp+27h+arg_18]
0x140027c78  jmp     loc_1400279A6
0x140027c7d  mov     eax, 0ACh
0x140027c82  lea     edx, [rax-4]
0x140027c85  jmp     loc_140027A4F
0x140027c8a  xor     edx, edx
0x140027c8c  mov     ebx, 1409h
0x140027c91  jmp     loc_140027AB2
0x140027c96  test    rcx, rcx
0x140027c99  jnz     short loc_140027CC8
0x140027c9b  mov     eax, ebx
0x140027c9d  jmp     loc_140027978
0x140027ca2  cmp     r14w, bx
0x140027ca6  jnz     short loc_140027CBB
0x140027ca8  mov     [rbp+27h+var_7C], ax
0x140027cac  mov     [rbp+27h+var_80], cx
0x140027cb0  jmp     loc_140027B01
0x140027cb5  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x140027cba  nop
0x140027cbb  mov     [rbp+27h+var_84], ax
0x140027cbf  mov     [rbp+27h+var_88], cx
0x140027cc3  jmp     loc_140027B01
0x140027cc8  mov     rax, [rdi+10h]
0x140027ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027cd1  jmp     short loc_140027C9B
0x140027cd3  mov     eax, 140Bh
0x140027cd8  jmp     loc_140027978
0x140027cdd  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x140027ce2  int     3; Trap to Debugger
0x140027ce3  mov     eax, 1801h
0x140027ce8  jmp     loc_140027978
```
