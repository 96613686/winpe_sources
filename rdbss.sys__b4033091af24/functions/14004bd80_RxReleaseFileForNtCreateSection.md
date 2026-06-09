# RxReleaseFileForNtCreateSection

- ea: `0x14004bd80`
- end: `0x14004beb7`
- name: `RxReleaseFileForNtCreateSection`
- size: `311`
- prototype: `void __stdcall(PFILE_OBJECT FileObject)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x140004180`
- `0x140009b80`
- `0x14000e770`
- `0x14000f2c0`
- `0x140010630`
- `0x140010730`
- `0x140016e70`
- `0x14004bd80`

## import_xrefs

- `ntoskrnl!MmIsFileSectionActive` at `0x14004be0b`
- `ntoskrnl!MmIsFileSectionActive` at `0x14004be0b`

## pseudocode

```c
void __stdcall RxReleaseFileForNtCreateSection(PFILE_OBJECT FileObject)
{
  PVPB Vpb; // rax
  ULONG_PTR v2; // rbx
  __int64 v3; // rdi
  __int64 v4; // rcx
  bool v5; // si
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  ULONG v9; // r8d
  const CHAR *v10; // r9
  __int64 v11; // rax
  _QWORD *v12; // rdx
  ULONG v13; // [rsp+20h] [rbp-8h]
  int v14; // [rsp+30h] [rbp+8h] BYREF

  Vpb = FileObject->Vpb;
  v2 = *(_QWORD *)&Vpb->SerialNumber;
  v3 = *(_QWORD *)Vpb->VolumeLabel;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids, v2);
  }
  if ( *(_QWORD *)(v2 + 128) )
    RxReleaseRundownDerefView(v2);
  v4 = *(_QWORD *)(v2 + 304);
  *(_DWORD *)(v2 + 156) &= ~0x40u;
  v14 = 0;
  MmIsFileSectionActive(v4 + 8, 7, &v14);
  v5 = v14 != 0;
  RxAcquirePowerContextLock(v6);
  if ( *(_DWORD *)(v2 + 460) )
  {
    *(_BYTE *)(v2 + 282) |= 0x80u;
    if ( (*(_BYTE *)(v2 + 282) & 2) != 0 && v5 )
    {
      LOBYTE(v8) = 4;
      LOBYTE(v7) = 2;
      RxUpdateFcbPowerState(v2, v7, v8);
    }
  }
  RxReleasePowerContextLock();
  v11 = *(_QWORD *)(v2 + 304);
  if ( *(_QWORD *)(v11 + 8) || *(_QWORD *)(v11 + 24) )
  {
    if ( (*(_DWORD *)(v3 + 72) & 0x400002) != 0 || (*(_DWORD *)(*(_QWORD *)(v3 + 32) + 120LL) & 1) == 0 )
      v12 = 0;
    else
      v12 = (_QWORD *)v3;
    RxSelectAndSwitchPagingFileObject(v2, v12, 0, 4u);
  }
  _RxReleaseFcb(0, (PMRX_FCB)v2, v9, v10, v13);
}

```

## disassembly

```asm
0x14004bd80  mov     [rsp+arg_8], rbx
0x14004bd85  mov     [rsp+arg_10], rsi
0x14004bd8a  push    rdi; SerialNumber
0x14004bd8b  sub     rsp, 20h
0x14004bd8f  mov     rax, [rcx+10h]
0x14004bd93  mov     rbx, [rax+18h]
0x14004bd97  mov     rdi, [rax+20h]
0x14004bd9b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bda2  lea     rax, WPP_GLOBAL_Control
0x14004bda9  cmp     rcx, rax
0x14004bdac  jz      short loc_14004BDD5
0x14004bdae  test    dword ptr [rcx+2Ch], 100h
0x14004bdb5  jz      short loc_14004BDD5
0x14004bdb7  cmp     byte ptr [rcx+29h], 2
0x14004bdbb  jb      short loc_14004BDD5
0x14004bdbd  mov     rcx, [rcx+18h]
0x14004bdc1  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x14004bdc8  mov     edx, 28h ; '('
0x14004bdcd  mov     r9, rbx
0x14004bdd0  call    WPP_SF_q
0x14004bdd5  cmp     qword ptr [rbx+80h], 0
0x14004bddd  jz      short loc_14004BDE7
0x14004bddf  mov     rcx, rbx
0x14004bde2  call    RxReleaseRundownDerefView
0x14004bde7  mov     rcx, [rbx+130h]
0x14004bdee  lea     r8, [rsp+28h+arg_0]
0x14004bdf3  and     dword ptr [rbx+9Ch], 0FFFFFFBFh
0x14004bdfa  add     rcx, 8
0x14004bdfe  mov     edx, 7
0x14004be03  mov     [rsp+28h+arg_0], 0
0x14004be0b  call    cs:__imp_MmIsFileSectionActive
0x14004be12  nop     dword ptr [rax+rax+00h]
0x14004be17  cmp     [rsp+28h+arg_0], 0
0x14004be1c  setnz   sil
0x14004be20  call    RxAcquirePowerContextLock
0x14004be25  cmp     dword ptr [rbx+1CCh], 0
0x14004be2c  jz      short loc_14004BE50
0x14004be2e  or      byte ptr [rbx+11Ah], 80h
0x14004be35  test    byte ptr [rbx+11Ah], 2
0x14004be3c  jz      short loc_14004BE50
0x14004be3e  test    sil, sil
0x14004be41  jz      short loc_14004BE50
0x14004be43  mov     r8b, 4
0x14004be46  mov     dl, 2
0x14004be48  mov     rcx, rbx
0x14004be4b  call    RxUpdateFcbPowerState
0x14004be50  call    RxReleasePowerContextLock
0x14004be55  mov     rax, [rbx+130h]
0x14004be5c  cmp     qword ptr [rax+8], 0
0x14004be61  jnz     short loc_14004BE6A
0x14004be63  cmp     qword ptr [rax+18h], 0
0x14004be68  jz      short loc_14004BE97
0x14004be6a  test    dword ptr [rdi+48h], 400002h
0x14004be71  jnz     short loc_14004BE84
0x14004be73  mov     rax, [rdi+20h]
0x14004be77  mov     ecx, [rax+78h]
0x14004be7a  test    cl, 1
0x14004be7d  jz      short loc_14004BE84
0x14004be7f  mov     rdx, rdi
0x14004be82  jmp     short loc_14004BE86
0x14004be84  xor     edx, edx
0x14004be86  mov     r9d, 4
0x14004be8c  xor     r8d, r8d
0x14004be8f  mov     rcx, rbx; BugCheckParameter3
0x14004be92  call    RxSelectAndSwitchPagingFileObject
0x14004be97  mov     rdx, rbx; MrxFcb
0x14004be9a  xor     ecx, ecx; RxContext
0x14004be9c  call    __RxReleaseFcb
0x14004bea1  mov     rbx, [rsp+28h+arg_8]
0x14004bea6  mov     eax, 126h
0x14004beab  mov     rsi, [rsp+28h+arg_10]
0x14004beb0  add     rsp, 20h
0x14004beb4  pop     rdi
0x14004beb5  retn
```
