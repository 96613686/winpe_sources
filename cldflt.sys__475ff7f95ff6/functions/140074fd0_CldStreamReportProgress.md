# CldStreamReportProgress

- ea: `0x140074fd0`
- end: `0x140075167`
- name: `CldStreamReportProgress`
- size: `407`
- prototype: `__int64 __fastcall(_QWORD *, KIRQL *, __int64, __int64, unsigned int, _BYTE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140074e1c`

## callees

- `0x140011400`
- `0x1400413c4`
- `0x140056770`
- `0x14006dc98`
- `0x140074fd0`
- `0x140075170`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x1400750bc`
- `ntoskrnl!PsGetProcessId` at `0x1400750bc`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400750ad`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400750ad`

## pseudocode

```c
__int64 __fastcall CldStreamReportProgress(_QWORD *a1, KIRQL *a2, __int64 a3, __int64 a4, unsigned int a5, _BYTE *a6)
{
  __int64 v6; // r15
  KIRQL *v8; // r13
  __int64 *v10; // rcx
  char v11; // r12
  KIRQL v12; // dl
  _QWORD *v13; // rsi
  _QWORD *v14; // r14
  _QWORD *v15; // rdi
  struct _KPROCESS *CurrentProcess; // rax
  _QWORD *v17; // rdi
  KIRQL *v18; // rdx

  v6 = a4;
  v8 = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qiiiiL(
      WPP_GLOBAL_Control->AttachedDevice,
      a5,
      a3,
      a1,
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)*a1 + 16LL) + 32LL),
      a2,
      a3,
      a4,
      a5);
  }
  v10 = a1 + 6;
  v11 = 1;
  LOBYTE(a2) = a3 != a1[5] || v6 > *v10;
  *v10 = v6;
  a1[5] = a3;
  *a6 = (_BYTE)a2;
  CldiStreamCdqACQUIRE((PFLT_CALLBACK_DATA_QUEUE)(*(_QWORD *)(*a1 + 8LL) + 144LL), a2);
  v13 = a1 + 2;
  v14 = (_QWORD *)a1[2];
  if ( v14 != a1 + 2 )
  {
    do
    {
      v15 = v14 - 1;
      CurrentProcess = IoGetCurrentProcess();
      if ( *((_DWORD *)v14 + 19) == (unsigned int)PsGetProcessId(CurrentProcess)
        && v15 != (_QWORD *)a1[7]
        && (!v8 || (KIRQL *)v15[7] == v8) )
      {
        *((_DWORD *)v15 + 20) = a5;
      }
      v14 = (_QWORD *)*v14;
    }
    while ( v14 != v13 );
    v6 = a4;
  }
  v17 = a1 + 7;
  if ( (_QWORD *)*v13 != v13 && !*v17 )
    v11 = 0;
  CldiStreamCdqRELEASE((PFLT_CALLBACK_DATA_QUEUE)(*(_QWORD *)(*a1 + 8LL) + 144LL), v12);
  if ( !v11 )
    return 0;
  if ( v6 >= a3 )
  {
    CldiStreamCompleteProviderRequest(a1, v18);
    return 0;
  }
  if ( *v17 )
    return 0;
  return CldiStreamBuildProviderRequest(a1, a3, v6, a5);
}

```

## disassembly

```asm
0x140074fd0  mov     r11, rsp
0x140074fd3  mov     [r11+10h], rbx
0x140074fd7  mov     [r11+20h], r9
0x140074fdb  push    rbp
0x140074fdc  push    rsi
0x140074fdd  push    rdi
0x140074fde  push    r12
0x140074fe0  push    r13
0x140074fe2  push    r14
0x140074fe4  push    r15
0x140074fe6  sub     rsp, 50h
0x140074fea  mov     r15, r9
0x140074fed  mov     [rsp+88h+arg_0], 0
0x140074ff8  mov     rbp, r8
0x140074ffb  mov     r13, rdx
0x140074ffe  mov     rbx, rcx
0x140075001  mov     rcx, cs:WPP_GLOBAL_Control
0x140075008  lea     rax, WPP_GLOBAL_Control
0x14007500f  cmp     rcx, rax
0x140075012  jz      short loc_140075058
0x140075014  test    dword ptr [rcx+2Ch], 100h
0x14007501b  jz      short loc_140075058
0x14007501d  cmp     byte ptr [rcx+29h], 4
0x140075021  jb      short loc_140075058
0x140075023  mov     rax, [rbx]
0x140075026  mov     rcx, [rcx+18h]
0x14007502a  mov     rdx, [rax]
0x14007502d  mov     rax, [rdx+10h]
0x140075031  mov     edx, [rsp+88h+arg_20]
0x140075038  mov     [rsp+88h+var_48], edx
0x14007503c  mov     [r11-50h], r9
0x140075040  mov     r9, rbx
0x140075043  mov     rax, [rax+20h]
0x140075047  mov     [r11-58h], r8
0x14007504b  mov     [r11-60h], r13
0x14007504f  mov     [r11-68h], rax
0x140075053  call    WPP_SF_qiiiiL
0x140075058  lea     rcx, [rbx+30h]
0x14007505c  mov     r12b, 1
0x14007505f  cmp     rbp, [rbx+28h]
0x140075063  jnz     short loc_14007506E
0x140075065  cmp     r15, [rcx]
0x140075068  jg      short loc_14007506E
0x14007506a  xor     dl, dl
0x14007506c  jmp     short loc_140075071
0x14007506e  mov     dl, r12b; Irql
0x140075071  mov     rax, [rsp+88h+arg_28]
0x140075079  mov     [rcx], r15
0x14007507c  mov     [rbx+28h], rbp
0x140075080  mov     [rax], dl
0x140075082  mov     rax, [rbx]
0x140075085  mov     rcx, [rax+8]
0x140075089  add     rcx, 90h; Cbdq
0x140075090  call    CldiStreamCdqACQUIRE
0x140075095  lea     rsi, [rbx+10h]
0x140075099  mov     r14, [rsi]
0x14007509c  cmp     r14, rsi
0x14007509f  jz      short loc_1400750F2
0x1400750a1  mov     r15d, [rsp+88h+arg_20]
0x1400750a9  lea     rdi, [r14-8]
0x1400750ad  call    cs:__imp_IoGetCurrentProcess
0x1400750b4  nop     dword ptr [rax+rax+00h]
0x1400750b9  mov     rcx, rax; Process
0x1400750bc  call    cs:__imp_PsGetProcessId
0x1400750c3  nop     dword ptr [rax+rax+00h]
0x1400750c8  cmp     [rdi+54h], eax
0x1400750cb  jnz     short loc_1400750E2
0x1400750cd  cmp     rdi, [rbx+38h]
0x1400750d1  jz      short loc_1400750E2
0x1400750d3  test    r13, r13
0x1400750d6  jz      short loc_1400750DE
0x1400750d8  cmp     [rdi+38h], r13
0x1400750dc  jnz     short loc_1400750E2
0x1400750de  mov     [rdi+50h], r15d
0x1400750e2  mov     r14, [r14]
0x1400750e5  cmp     r14, rsi
0x1400750e8  jnz     short loc_1400750A9
0x1400750ea  mov     r15, [rsp+88h+arg_18]
0x1400750f2  lea     rdi, [rbx+38h]
0x1400750f6  cmp     [rsi], rsi
0x1400750f9  jz      short loc_140075104
0x1400750fb  cmp     qword ptr [rdi], 0
0x1400750ff  jnz     short loc_140075104
0x140075101  xor     r12b, r12b
0x140075104  mov     rax, [rbx]
0x140075107  mov     rcx, [rax+8]
0x14007510b  add     rcx, 90h; Cbdq
0x140075112  call    CldiStreamCdqRELEASE
0x140075117  test    r12b, r12b
0x14007511a  jz      short loc_140075129
0x14007511c  cmp     r15, rbp
0x14007511f  jl      short loc_140075149
0x140075121  mov     rcx, rbx
0x140075124  call    CldiStreamCompleteProviderRequest
0x140075129  mov     eax, [rsp+88h+arg_0]
0x140075130  mov     rbx, [rsp+88h+arg_8]
0x140075138  add     rsp, 50h
0x14007513c  pop     r15
0x14007513e  pop     r14
0x140075140  pop     r13
0x140075142  pop     r12
0x140075144  pop     rdi
0x140075145  pop     rsi
0x140075146  pop     rbp
0x140075147  retn
0x140075149  cmp     qword ptr [rdi], 0
0x14007514d  jnz     short loc_140075129
0x14007514f  mov     r9d, [rsp+88h+arg_20]
0x140075157  mov     r8, r15
0x14007515a  mov     rdx, rbp
0x14007515d  mov     rcx, rbx
0x140075160  call    CldiStreamBuildProviderRequest
0x140075165  jmp     short loc_140075130
```
