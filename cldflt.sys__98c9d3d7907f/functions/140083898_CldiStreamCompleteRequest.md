# CldiStreamCompleteRequest

- ea: `0x140083898`
- end: `0x140083adf`
- name: `CldiStreamCompleteRequest`
- size: `583`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140041700`
- `0x140041be8`
- `0x140041ca0`
- `0x14006d078`
- `0x14006db78`

## callees

- `0x140003c50`
- `0x140009ae8`
- `0x14000c960`
- `0x140010bb4`
- `0x140010cdc`
- `0x14001e220`
- `0x140075050`
- `0x1400819ac`
- `0x140083898`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400839da`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400839da`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400839ce`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400839ce`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14008399c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14008399c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140083987`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140083987`
- `FLTMGR!FltCbdqRemoveIo` at `0x14008395f`
- `FLTMGR!FltCbdqRemoveIo` at `0x14008395f`

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
  __int64 v15; // r8
  __int64 v16; // [rsp+88h] [rbp+10h]

  v4 = a4;
  v5 = *(__int64 **)(a2 + 96);
  v6 = a3;
  v7 = *(_QWORD *)(a2 + 160);
  v9 = *(void (__fastcall **)(__int64, _QWORD, _QWORD))(a2 + 152);
  v16 = v7;
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
        if ( !FltCbdqRemoveIo(
                (PFLT_CALLBACK_DATA_QUEUE)(*(_QWORD *)(*a1 + 8LL) + 144LL),
                (PFLT_CALLBACK_DATA_QUEUE_IO_CONTEXT)(*(_QWORD *)(a2 + 96) + 8LL)) )
        {
          v6 = -1073741536;
          HsmDbgBreakOnStatus(3221225760LL);
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
        v7 = v16;
      }
    }
  }
  if ( (_QWORD *)a1[2] == a1 + 2 )
  {
    a1[6] = 0;
    a1[5] = 0;
  }
  if ( !*(_BYTE *)(a2 + 105) )
    CldiStreamCdqRELEASE((PFLT_CALLBACK_DATA_QUEUE)(*(_QWORD *)(*a1 + 8LL) + 144LL), a2);
  CldiStreamDeleteRequest((char *)a2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_iqqd(WPP_GLOBAL_Control->AttachedDevice, 19, v15, v11, a2, v12, v6);
  }
  if ( v9 )
    v9(v7, v6, v4);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_iqqd(WPP_GLOBAL_Control->AttachedDevice, 20, v15, v11, a2, v12, v6);
  }
}

```

## disassembly

```asm
0x140083898  mov     r11, rsp
0x14008389b  mov     [r11+18h], rbx
0x14008389f  mov     [r11+20h], r9d
0x1400838a3  push    rbp
0x1400838a4  push    rsi
0x1400838a5  push    rdi
0x1400838a6  push    r12
0x1400838a8  push    r13
0x1400838aa  push    r14
0x1400838ac  push    r15
0x1400838ae  sub     rsp, 40h
0x1400838b2  mov     rax, [rcx]
0x1400838b5  mov     esi, r9d
0x1400838b8  mov     rdi, [rdx+60h]
0x1400838bc  mov     r12d, r8d
0x1400838bf  mov     r14, [rdx+0A0h]
0x1400838c6  mov     rbp, rdx
0x1400838c9  mov     rbx, [rdx+98h]
0x1400838d0  mov     r15, rcx
0x1400838d3  mov     r10, [rax]
0x1400838d6  mov     [rsp+78h+arg_8], r14
0x1400838de  mov     rax, [r10+10h]
0x1400838e2  mov     r13, [rax+20h]
0x1400838e6  lea     rax, WPP_GLOBAL_Control
0x1400838ed  test    rdi, rdi
0x1400838f0  jz      loc_1400839F7
0x1400838f6  cmp     byte ptr [rdx+69h], 0
0x1400838fa  jnz     loc_1400839F7
0x140083900  mov     rdi, [rdi]
0x140083903  test    rdi, rdi
0x140083906  jz      loc_1400839F9
0x14008390c  lea     rsi, [rdi+30h]
0x140083910  cmp     [rsi], rsi
0x140083913  jnz     short loc_140083987
0x140083915  mov     rcx, cs:WPP_GLOBAL_Control
0x14008391c  cmp     rcx, rax
0x14008391f  jz      short loc_140083949
0x140083921  test    dword ptr [rcx+2Ch], 100h
0x140083928  jz      short loc_140083949
0x14008392a  cmp     byte ptr [rcx+29h], 4
0x14008392e  jb      short loc_140083949
0x140083930  mov     rcx, [rcx+18h]
0x140083934  mov     edx, 12h
0x140083939  mov     [r11-50h], rdi
0x14008393d  mov     r9, r13
0x140083940  mov     [r11-58h], rbp
0x140083944  call    WPP_SF_qqi
0x140083949  mov     rax, [r15]
0x14008394c  mov     rdx, [rbp+60h]
0x140083950  add     rdx, 8; Context
0x140083954  mov     rcx, [rax+8]
0x140083958  add     rcx, 90h; Cbdq
0x14008395f  call    cs:__imp_FltCbdqRemoveIo
0x140083966  nop     dword ptr [rax+rax+00h]
0x14008396b  test    rax, rax
0x14008396e  jnz     short loc_14008397E
0x140083970  mov     r12d, 0C0000120h
0x140083976  mov     ecx, r12d
0x140083979  call    HsmDbgBreakOnStatus
0x14008397e  mov     esi, [rsp+78h+arg_18]
0x140083985  jmp     short loc_1400839F9
0x140083987  call    cs:__imp_KeEnterCriticalRegion
0x14008398e  nop     dword ptr [rax+rax+00h]
0x140083993  mov     dl, 1; Wait
0x140083995  lea     rcx, Resource; Resource
0x14008399c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400839a3  nop     dword ptr [rax+rax+00h]
0x1400839a8  mov     r14, [rsi]
0x1400839ab  jmp     short loc_1400839C2
0x1400839ad  lea     rcx, [r14-18h]
0x1400839b1  call    CldiStreamRemoveFromGlobalRequestListNoLock
0x1400839b6  lea     rcx, [r14-18h]
0x1400839ba  call    CldiStreamInsertIntoGlobalRequestListNoLock
0x1400839bf  mov     r14, [r14]
0x1400839c2  cmp     r14, rsi
0x1400839c5  jnz     short loc_1400839AD
0x1400839c7  lea     rcx, Resource; Resource
0x1400839ce  call    cs:__imp_ExReleaseResourceLite
0x1400839d5  nop     dword ptr [rax+rax+00h]
0x1400839da  call    cs:__imp_KeLeaveCriticalRegion
0x1400839e1  nop     dword ptr [rax+rax+00h]
0x1400839e6  mov     esi, [rsp+78h+arg_18]
0x1400839ed  mov     r14, [rsp+78h+arg_8]
0x1400839f5  jmp     short loc_1400839F9
0x1400839f7  xor     edi, edi
0x1400839f9  lea     rax, [r15+10h]
0x1400839fd  cmp     [rax], rax
0x140083a00  jnz     short loc_140083A12
0x140083a02  mov     qword ptr [r15+30h], 0
0x140083a0a  mov     qword ptr [r15+28h], 0
0x140083a12  cmp     byte ptr [rbp+69h], 0
0x140083a16  jnz     short loc_140083A2B
0x140083a18  mov     rax, [r15]
0x140083a1b  mov     rcx, [rax+8]
0x140083a1f  add     rcx, 90h; Cbdq
0x140083a26  call    CldiStreamCdqRELEASE
0x140083a2b  mov     rcx, rbp; Entry
0x140083a2e  call    CldiStreamDeleteRequest
0x140083a33  mov     rcx, cs:WPP_GLOBAL_Control
0x140083a3a  lea     r15, WPP_GLOBAL_Control
0x140083a41  cmp     rcx, r15
0x140083a44  jz      short loc_140083A75
0x140083a46  test    dword ptr [rcx+2Ch], 100h
0x140083a4d  jz      short loc_140083A75
0x140083a4f  cmp     byte ptr [rcx+29h], 4
0x140083a53  jb      short loc_140083A75
0x140083a55  mov     rcx, [rcx+18h]
0x140083a59  mov     edx, 13h
0x140083a5e  mov     [rsp+78h+var_48], r12d
0x140083a63  mov     r9, r13
0x140083a66  mov     [rsp+78h+var_50], rdi
0x140083a6b  mov     [rsp+78h+var_58], rbp
0x140083a70  call    WPP_SF_iqqd
0x140083a75  test    rbx, rbx
0x140083a78  jz      short loc_140083A8B
0x140083a7a  mov     r8d, esi
0x140083a7d  mov     edx, r12d
0x140083a80  mov     rcx, r14
0x140083a83  mov     rax, rbx
0x140083a86  call    _guard_dispatch_icall
0x140083a8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140083a92  cmp     rcx, r15
0x140083a95  jz      short loc_140083AC6
0x140083a97  test    dword ptr [rcx+2Ch], 100h
0x140083a9e  jz      short loc_140083AC6
0x140083aa0  cmp     byte ptr [rcx+29h], 4
0x140083aa4  jb      short loc_140083AC6
0x140083aa6  mov     rcx, [rcx+18h]
0x140083aaa  mov     edx, 14h
0x140083aaf  mov     [rsp+78h+var_48], r12d
0x140083ab4  mov     r9, r13
0x140083ab7  mov     [rsp+78h+var_50], rdi
0x140083abc  mov     [rsp+78h+var_58], rbp
0x140083ac1  call    WPP_SF_iqqd
0x140083ac6  mov     rbx, [rsp+78h+arg_10]
0x140083ace  add     rsp, 40h
0x140083ad2  pop     r15
0x140083ad4  pop     r14
0x140083ad6  pop     r13
0x140083ad8  pop     r12
0x140083ada  pop     rdi
0x140083adb  pop     rsi
0x140083adc  pop     rbp
0x140083add  retn
```
