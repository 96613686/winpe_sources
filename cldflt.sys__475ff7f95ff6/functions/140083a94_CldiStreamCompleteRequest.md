# CldiStreamCompleteRequest

- ea: `0x140083a94`
- end: `0x140083ca0`
- name: `CldiStreamCompleteRequest`
- size: `524`
- prototype: `void __fastcall(_QWORD *, __int64, __int64, unsigned int)`
- caller_count: `5`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140041754`
- `0x140041cbc`
- `0x140041d84`
- `0x14006d198`
- `0x14006dc98`

## callees

- `0x140009ae8`
- `0x14000c960`
- `0x140010c34`
- `0x140010d5c`
- `0x14001e2a0`
- `0x140075170`
- `0x140081b4c`
- `0x140083a94`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140083ba1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140083ba1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140083b95`
- `ntoskrnl!ExReleaseResourceLite` at `0x140083b95`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140083b63`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140083b63`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140083b4e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140083b4e`

## pseudocode

```c
void __fastcall CldiStreamCompleteRequest(_QWORD *a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned int v4; // esi
  __int64 *v5; // rdi
  unsigned int v6; // r12d
  __int64 v7; // r14
  void (__fastcall *v9)(__int64, _QWORD, _QWORD); // rbx
  __int64 v11; // r13
  __int64 v12; // rdi
  _QWORD **v13; // rsi
  _QWORD *i; // r14
  KIRQL v15; // dl
  __int64 v16; // r8
  __int64 v17; // [rsp+88h] [rbp+10h]

  v4 = a4;
  v5 = *(__int64 **)(a2 + 96);
  v6 = a3;
  v7 = *(_QWORD *)(a2 + 160);
  v9 = *(void (__fastcall **)(__int64, _QWORD, _QWORD))(a2 + 152);
  v17 = v7;
  v11 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)*a1 + 16LL) + 32LL);
  if ( !v5 || *(_BYTE *)(a2 + 105) )
  {
    v12 = 0;
  }
  else
  {
    v12 = *v5;
    if ( v12 )
    {
      v13 = (_QWORD **)(v12 + 48);
      if ( *v13 == v13 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qqi(WPP_GLOBAL_Control->AttachedDevice, 18, a3, v11, a2, v12);
        }
        v4 = a4;
      }
      else
      {
        KeEnterCriticalRegion();
        ExAcquireResourceExclusiveLite(&Resource, 1u);
        for ( i = *v13; i != v13; i = (_QWORD *)*i )
        {
          CldiStreamRemoveFromGlobalRequestListNoLock(i - 3);
          CldiStreamInsertIntoGlobalRequestListNoLock(i - 3);
        }
        ExReleaseResourceLite(&Resource);
        KeLeaveCriticalRegion();
        v4 = a4;
        v7 = v17;
      }
    }
  }
  if ( (_QWORD *)a1[2] == a1 + 2 )
  {
    a1[6] = 0;
    a1[5] = 0;
  }
  CldiStreamDeleteRequest((PVOID)a2);
  CldiStreamCdqRELEASE((PFLT_CALLBACK_DATA_QUEUE)(*(_QWORD *)(*a1 + 8LL) + 144LL), v15);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_iqqd(WPP_GLOBAL_Control->AttachedDevice, 19, v16, v11, a2, v12, v6);
  }
  if ( v9 )
    v9(v7, v6, v4);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_iqqd(WPP_GLOBAL_Control->AttachedDevice, 20, v16, v11, a2, v12, v6);
  }
}

```

## disassembly

```asm
0x140083a94  mov     r11, rsp
0x140083a97  mov     [r11+18h], rbx
0x140083a9b  mov     [r11+20h], r9d
0x140083a9f  push    rbp
0x140083aa0  push    rsi
0x140083aa1  push    rdi
0x140083aa2  push    r12
0x140083aa4  push    r13
0x140083aa6  push    r14
0x140083aa8  push    r15
0x140083aaa  sub     rsp, 40h
0x140083aae  mov     rax, [rcx]
0x140083ab1  mov     esi, r9d
0x140083ab4  mov     rdi, [rdx+60h]
0x140083ab8  mov     r12d, r8d
0x140083abb  mov     r14, [rdx+0A0h]
0x140083ac2  mov     rbp, rdx
0x140083ac5  mov     rbx, [rdx+98h]
0x140083acc  mov     r15, rcx
0x140083acf  mov     r10, [rax]
0x140083ad2  mov     [rsp+78h+arg_8], r14
0x140083ada  mov     rax, [r10+10h]
0x140083ade  mov     r13, [rax+20h]
0x140083ae2  lea     rax, WPP_GLOBAL_Control
0x140083ae9  test    rdi, rdi
0x140083aec  jz      loc_140083BBE
0x140083af2  cmp     byte ptr [rdx+69h], 0
0x140083af6  jnz     loc_140083BBE
0x140083afc  mov     rdi, [rdi]
0x140083aff  test    rdi, rdi
0x140083b02  jz      loc_140083BC0
0x140083b08  lea     rsi, [rdi+30h]
0x140083b0c  cmp     [rsi], rsi
0x140083b0f  jnz     short loc_140083B4E
0x140083b11  mov     rcx, cs:WPP_GLOBAL_Control
0x140083b18  cmp     rcx, rax
0x140083b1b  jz      short loc_140083B45
0x140083b1d  test    dword ptr [rcx+2Ch], 100h
0x140083b24  jz      short loc_140083B45
0x140083b26  cmp     byte ptr [rcx+29h], 4
0x140083b2a  jb      short loc_140083B45
0x140083b2c  mov     rcx, [rcx+18h]
0x140083b30  mov     edx, 12h
0x140083b35  mov     [r11-50h], rdi
0x140083b39  mov     r9, r13
0x140083b3c  mov     [r11-58h], rbp
0x140083b40  call    WPP_SF_qqi
0x140083b45  mov     esi, [rsp+78h+arg_18]
0x140083b4c  jmp     short loc_140083BC0
0x140083b4e  call    cs:__imp_KeEnterCriticalRegion
0x140083b55  nop     dword ptr [rax+rax+00h]
0x140083b5a  mov     dl, 1; Wait
0x140083b5c  lea     rcx, Resource; Resource
0x140083b63  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140083b6a  nop     dword ptr [rax+rax+00h]
0x140083b6f  mov     r14, [rsi]
0x140083b72  jmp     short loc_140083B89
0x140083b74  lea     rcx, [r14-18h]
0x140083b78  call    CldiStreamRemoveFromGlobalRequestListNoLock
0x140083b7d  lea     rcx, [r14-18h]
0x140083b81  call    CldiStreamInsertIntoGlobalRequestListNoLock
0x140083b86  mov     r14, [r14]
0x140083b89  cmp     r14, rsi
0x140083b8c  jnz     short loc_140083B74
0x140083b8e  lea     rcx, Resource; Resource
0x140083b95  call    cs:__imp_ExReleaseResourceLite
0x140083b9c  nop     dword ptr [rax+rax+00h]
0x140083ba1  call    cs:__imp_KeLeaveCriticalRegion
0x140083ba8  nop     dword ptr [rax+rax+00h]
0x140083bad  mov     esi, [rsp+78h+arg_18]
0x140083bb4  mov     r14, [rsp+78h+arg_8]
0x140083bbc  jmp     short loc_140083BC0
0x140083bbe  xor     edi, edi
0x140083bc0  lea     rax, [r15+10h]
0x140083bc4  cmp     [rax], rax
0x140083bc7  jnz     short loc_140083BD9
0x140083bc9  mov     qword ptr [r15+30h], 0
0x140083bd1  mov     qword ptr [r15+28h], 0
0x140083bd9  mov     rcx, rbp; Entry
0x140083bdc  call    CldiStreamDeleteRequest
0x140083be1  mov     rax, [r15]
0x140083be4  mov     rcx, [rax+8]
0x140083be8  add     rcx, 90h; Cbdq
0x140083bef  call    CldiStreamCdqRELEASE
0x140083bf4  mov     rcx, cs:WPP_GLOBAL_Control
0x140083bfb  lea     r15, WPP_GLOBAL_Control
0x140083c02  cmp     rcx, r15
0x140083c05  jz      short loc_140083C36
0x140083c07  test    dword ptr [rcx+2Ch], 100h
0x140083c0e  jz      short loc_140083C36
0x140083c10  cmp     byte ptr [rcx+29h], 4
0x140083c14  jb      short loc_140083C36
0x140083c16  mov     rcx, [rcx+18h]
0x140083c1a  mov     edx, 13h
0x140083c1f  mov     [rsp+78h+var_48], r12d
0x140083c24  mov     r9, r13
0x140083c27  mov     [rsp+78h+var_50], rdi
0x140083c2c  mov     [rsp+78h+var_58], rbp
0x140083c31  call    WPP_SF_iqqd
0x140083c36  test    rbx, rbx
0x140083c39  jz      short loc_140083C4C
0x140083c3b  mov     r8d, esi
0x140083c3e  mov     edx, r12d
0x140083c41  mov     rcx, r14
0x140083c44  mov     rax, rbx
0x140083c47  call    _guard_dispatch_icall
0x140083c4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140083c53  cmp     rcx, r15
0x140083c56  jz      short loc_140083C87
0x140083c58  test    dword ptr [rcx+2Ch], 100h
0x140083c5f  jz      short loc_140083C87
0x140083c61  cmp     byte ptr [rcx+29h], 4
0x140083c65  jb      short loc_140083C87
0x140083c67  mov     rcx, [rcx+18h]
0x140083c6b  mov     edx, 14h
0x140083c70  mov     [rsp+78h+var_48], r12d
0x140083c75  mov     r9, r13
0x140083c78  mov     [rsp+78h+var_50], rdi
0x140083c7d  mov     [rsp+78h+var_58], rbp
0x140083c82  call    WPP_SF_iqqd
0x140083c87  mov     rbx, [rsp+78h+arg_10]
0x140083c8f  add     rsp, 40h
0x140083c93  pop     r15
0x140083c95  pop     r14
0x140083c97  pop     r13
0x140083c99  pop     r12
0x140083c9b  pop     rdi
0x140083c9c  pop     rsi
0x140083c9d  pop     rbp
0x140083c9e  retn
```
