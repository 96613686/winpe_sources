# CldStreamReportProgress

- ea: `0x140074eb0`
- end: `0x140075047`
- name: `CldStreamReportProgress`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140074cfc`

## callees

- `0x140011380`
- `0x1400413b4`
- `0x140056650`
- `0x14006db78`
- `0x140074eb0`
- `0x140075050`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x140074f9c`
- `ntoskrnl!PsGetProcessId` at `0x140074f9c`
- `ntoskrnl!IoGetCurrentProcess` at `0x140074f8d`
- `ntoskrnl!IoGetCurrentProcess` at `0x140074f8d`

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
    CldiStreamCompleteProviderRequest(a1);
    return 0;
  }
  if ( *v17 )
    return 0;
  return CldiStreamBuildProviderRequest(a1, a3, v6, a5);
}

```

## disassembly

```asm
0x140074eb0  mov     r11, rsp
0x140074eb3  mov     [r11+10h], rbx
0x140074eb7  mov     [r11+20h], r9
0x140074ebb  push    rbp
0x140074ebc  push    rsi
0x140074ebd  push    rdi
0x140074ebe  push    r12
0x140074ec0  push    r13
0x140074ec2  push    r14
0x140074ec4  push    r15
0x140074ec6  sub     rsp, 50h
0x140074eca  mov     r15, r9
0x140074ecd  mov     [rsp+88h+arg_0], 0
0x140074ed8  mov     rbp, r8
0x140074edb  mov     r13, rdx
0x140074ede  mov     rbx, rcx
0x140074ee1  mov     rcx, cs:WPP_GLOBAL_Control
0x140074ee8  lea     rax, WPP_GLOBAL_Control
0x140074eef  cmp     rcx, rax
0x140074ef2  jz      short loc_140074F38
0x140074ef4  test    dword ptr [rcx+2Ch], 100h
0x140074efb  jz      short loc_140074F38
0x140074efd  cmp     byte ptr [rcx+29h], 4
0x140074f01  jb      short loc_140074F38
0x140074f03  mov     rax, [rbx]
0x140074f06  mov     rcx, [rcx+18h]
0x140074f0a  mov     rdx, [rax]
0x140074f0d  mov     rax, [rdx+10h]
0x140074f11  mov     edx, [rsp+88h+arg_20]
0x140074f18  mov     [rsp+88h+var_48], edx
0x140074f1c  mov     [r11-50h], r9
0x140074f20  mov     r9, rbx
0x140074f23  mov     rax, [rax+20h]
0x140074f27  mov     [r11-58h], r8
0x140074f2b  mov     [r11-60h], r13
0x140074f2f  mov     [r11-68h], rax
0x140074f33  call    WPP_SF_qiiiiL
0x140074f38  lea     rcx, [rbx+30h]
0x140074f3c  mov     r12b, 1
0x140074f3f  cmp     rbp, [rbx+28h]
0x140074f43  jnz     short loc_140074F4E
0x140074f45  cmp     r15, [rcx]
0x140074f48  jg      short loc_140074F4E
0x140074f4a  xor     dl, dl
0x140074f4c  jmp     short loc_140074F51
0x140074f4e  mov     dl, r12b; Irql
0x140074f51  mov     rax, [rsp+88h+arg_28]
0x140074f59  mov     [rcx], r15
0x140074f5c  mov     [rbx+28h], rbp
0x140074f60  mov     [rax], dl
0x140074f62  mov     rax, [rbx]
0x140074f65  mov     rcx, [rax+8]
0x140074f69  add     rcx, 90h; Cbdq
0x140074f70  call    CldiStreamCdqACQUIRE
0x140074f75  lea     rsi, [rbx+10h]
0x140074f79  mov     r14, [rsi]
0x140074f7c  cmp     r14, rsi
0x140074f7f  jz      short loc_140074FD2
0x140074f81  mov     r15d, [rsp+88h+arg_20]
0x140074f89  lea     rdi, [r14-8]
0x140074f8d  call    cs:__imp_IoGetCurrentProcess
0x140074f94  nop     dword ptr [rax+rax+00h]
0x140074f99  mov     rcx, rax; Process
0x140074f9c  call    cs:__imp_PsGetProcessId
0x140074fa3  nop     dword ptr [rax+rax+00h]
0x140074fa8  cmp     [rdi+54h], eax
0x140074fab  jnz     short loc_140074FC2
0x140074fad  cmp     rdi, [rbx+38h]
0x140074fb1  jz      short loc_140074FC2
0x140074fb3  test    r13, r13
0x140074fb6  jz      short loc_140074FBE
0x140074fb8  cmp     [rdi+38h], r13
0x140074fbc  jnz     short loc_140074FC2
0x140074fbe  mov     [rdi+50h], r15d
0x140074fc2  mov     r14, [r14]
0x140074fc5  cmp     r14, rsi
0x140074fc8  jnz     short loc_140074F89
0x140074fca  mov     r15, [rsp+88h+arg_18]
0x140074fd2  lea     rdi, [rbx+38h]
0x140074fd6  cmp     [rsi], rsi
0x140074fd9  jz      short loc_140074FE4
0x140074fdb  cmp     qword ptr [rdi], 0
0x140074fdf  jnz     short loc_140074FE4
0x140074fe1  xor     r12b, r12b
0x140074fe4  mov     rax, [rbx]
0x140074fe7  mov     rcx, [rax+8]
0x140074feb  add     rcx, 90h; Cbdq
0x140074ff2  call    CldiStreamCdqRELEASE
0x140074ff7  test    r12b, r12b
0x140074ffa  jz      short loc_140075009
0x140074ffc  cmp     r15, rbp
0x140074fff  jl      short loc_140075029
0x140075001  mov     rcx, rbx
0x140075004  call    CldiStreamCompleteProviderRequest
0x140075009  mov     eax, [rsp+88h+arg_0]
0x140075010  mov     rbx, [rsp+88h+arg_8]
0x140075018  add     rsp, 50h
0x14007501c  pop     r15
0x14007501e  pop     r14
0x140075020  pop     r13
0x140075022  pop     r12
0x140075024  pop     rdi
0x140075025  pop     rsi
0x140075026  pop     rbp
0x140075027  retn
0x140075029  cmp     qword ptr [rdi], 0
0x14007502d  jnz     short loc_140075009
0x14007502f  mov     r9d, [rsp+88h+arg_20]
0x140075037  mov     r8, r15
0x14007503a  mov     rdx, rbp
0x14007503d  mov     rcx, rbx
0x140075040  call    CldiStreamBuildProviderRequest
0x140075045  jmp     short loc_140075010
```
