# KsecDeviceControl

- ea: `0x180026f68`
- end: `0x18002728a`
- name: `KsecDeviceControl`
- size: `802`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int, _DWORD *, unsigned int *, int, PIRP Irp)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180026d90`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x180001f90`
- `0x180002820`
- `0x180005b58`
- `0x180005e94`
- `0x180006bf4`
- `0x180007bd8`
- `0x180010920`
- `0x180022b44`
- `0x180023080`
- `0x180026f68`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x18002717b`
- `ntoskrnl!ObOpenObjectByPointer` at `0x18002717b`
- `ntoskrnl!IoGetRequestorProcess` at `0x180026f9a`
- `ntoskrnl!IoGetRequestorProcess` at `0x180026f9a`
- `ntoskrnl!ObfReferenceObject` at `0x18002712f`
- `ntoskrnl!ObfReferenceObject` at `0x18002712f`
- `ntoskrnl!ExGetPreviousMode` at `0x18002724e`
- `ntoskrnl!ExGetPreviousMode` at `0x18002724e`
- `ntoskrnl!IoIs32bitProcess` at `0x1800271d2`
- `ntoskrnl!IoIs32bitProcess` at `0x1800271d2`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x18002722c`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x18002722c`
- `ntoskrnl!PsGetCurrentProcess` at `0x180027111`
- `ntoskrnl!PsGetCurrentProcess` at `0x180027111`
- `ntoskrnl!ZwClose` at `0x18002723d`
- `ntoskrnl!ZwClose` at `0x18002723d`

## pseudocode

```c
__int64 __fastcall KsecDeviceControl(
        unsigned int *a1,
        unsigned int a2,
        _DWORD *a3,
        unsigned int *a4,
        unsigned int a5,
        PIRP Irp)
{
  PIRP v6; // rdi
  PEPROCESS RequestorProcess; // rax
  struct _EPROCESS *v12; // r15
  int QueuedFunctionCalls; // eax
  int Client; // ebx
  bool v16; // zf
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  _QWORD *v22; // rax
  void *v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  PVOID *v28; // rax
  void *v29; // rdx
  void *v30; // rax
  void *v31; // rdi
  ULONG_PTR RegionSize; // [rsp+40h] [rbp-10h] BYREF
  PVOID BaseAddress; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v34; // [rsp+98h] [rbp+48h] BYREF

  v6 = Irp;
  v34 = 0;
  RequestorProcess = IoGetRequestorProcess(Irp);
  v12 = RequestorProcess;
  switch ( a5 )
  {
    case 0x390038u:
      if ( ExGetPreviousMode() )
      {
        Client = -1073741790;
        break;
      }
      if ( a1 && a2 == 16 )
      {
        QueuedFunctionCalls = KsecRegisterExtension(*a1, *((_QWORD *)a1 + 1));
        goto LABEL_9;
      }
      goto LABEL_12;
    case 0x390058u:
      v16 = v6->RequestorMode == 1;
      BaseAddress = 0;
      RegionSize = 0;
      if ( !v16 || !RequestorProcess || !a1 )
        goto LABEL_12;
      if ( IoIs32bitProcess(v6) )
      {
        if ( a2 != 4 )
          goto LABEL_12;
        v29 = (void *)*a1;
      }
      else
      {
        if ( a2 != 8 )
          goto LABEL_12;
        v29 = *(void **)a1;
      }
      BaseAddress = v29;
      v30 = (void *)KsecRemoveValidVm(v12, (unsigned __int8 *)v29);
      v31 = v30;
      if ( v30 )
      {
        RegionSize = 0;
        Client = ZwFreeVirtualMemory(v30, &BaseAddress, &RegionSize, 0x8000u);
        ZwClose(v31);
        break;
      }
      goto LABEL_12;
    case 0x39006Au:
      QueuedFunctionCalls = IoctlIpcGetQueuedFunctionCalls(v6);
      goto LABEL_9;
    case 0x39006Fu:
      CurrentStackLocation = v6->Tail.Overlay.CurrentStackLocation;
      if ( CurrentStackLocation )
      {
        QueuedFunctionCalls = KsecIoctlHandleFunctionReturn(
                                CurrentStackLocation->Parameters.CreatePipe.Parameters,
                                CurrentStackLocation->Parameters.Create.Options);
        goto LABEL_9;
      }
LABEL_12:
      Client = -1073741811;
      break;
    case 0x398000u:
      KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&RegionSize);
      if ( KsecddLsaStateRef::IsValid((KsecddLsaStateRef *)&RegionSize) )
      {
        if ( *(_QWORD *)KsecddLsaStateRef::operator _KSECDDLSASTATE *(&RegionSize) )
        {
          Client = -1073741637;
        }
        else if ( a3 && *a4 >= 4 )
        {
          PsGetCurrentProcess(v19, v18, v20, v21);
          v22 = (_QWORD *)KsecddLsaStateRef::operator _KSECDDLSASTATE *(&RegionSize);
          *v22 = v23;
          ObfReferenceObject(v23);
          LOBYTE(v24) = 1;
          LOBYTE(v25) = 1;
          Client = CreateClient(v25, v24, v26, v27);
          if ( Client >= 0 )
          {
            v28 = (PVOID *)KsecddLsaStateRef::operator _KSECDDLSASTATE *(&RegionSize);
            Client = ObOpenObjectByPointer(*v28, 0x200u, 0, 0x478u, 0, 0, v28 + 1);
            if ( Client >= 0 )
            {
              *a3 = KsecSystemProcessId;
              v34 = 4;
            }
          }
        }
        else
        {
          Client = -1073741789;
        }
      }
      else
      {
        Client = -1073741058;
      }
      KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&RegionSize);
      break;
    default:
      if ( WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink && WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink->Flink )
      {
        v34 = *a4;
        QueuedFunctionCalls = ((__int64 (__fastcall *)(unsigned int *, _QWORD, _DWORD *, unsigned int *, unsigned int, KPROCESSOR_MODE))WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink->Flink)(
                                a1,
                                a2,
                                a3,
                                &v34,
                                a5,
                                v6->RequestorMode);
LABEL_9:
        Client = QueuedFunctionCalls;
        break;
      }
      Client = -1073741822;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 31, WPP_47798432cc4f3443573e38da5669f213_Traceguids, a5);
      break;
  }
  *a4 = v34;
  return (unsigned int)Client;
}

```

## disassembly

```asm
0x180026f68  mov     [rsp-28h+arg_0], rbx
0x180026f6d  mov     [rsp-28h+arg_8], rsi
0x180026f72  push    rbp
0x180026f73  push    rdi
0x180026f74  push    r12
0x180026f76  push    r14
0x180026f78  push    r15
0x180026f7a  mov     rbp, rsp
0x180026f7d  sub     rsp, 50h
0x180026f81  mov     rdi, [rbp+Irp]
0x180026f85  mov     rbx, rcx
0x180026f88  mov     rcx, rdi; Irp
0x180026f8b  mov     [rbp+arg_18], 0
0x180026f92  mov     r12, r9
0x180026f95  mov     r14, r8
0x180026f98  mov     esi, edx
0x180026f9a  call    cs:__imp_IoGetRequestorProcess
0x180026fa1  nop     dword ptr [rax+rax+00h]
0x180026fa6  mov     r9d, [rbp+arg_20]
0x180026faa  mov     r10d, r9d
0x180026fad  mov     r15, rax
0x180026fb0  sub     r10d, 390038h
0x180026fb7  jz      loc_18002724E
0x180026fbd  sub     r10d, 20h ; ' '
0x180026fc1  jz      loc_18002704E
0x180026fc7  sub     r10d, 12h
0x180026fcb  jz      loc_1800271B0
0x180026fd1  sub     r10d, 5
0x180026fd5  jz      loc_18002706F
0x180026fdb  cmp     r10d, 7F91h
0x180026fe2  jz      loc_1800270C2
0x180026fe8  mov     rcx, cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x180026fef  test    rcx, rcx
0x180026ff2  jz      loc_180027089
0x180026ff8  cmp     qword ptr [rcx], 0
0x180026ffc  jz      loc_180027089
0x180027002  mov     eax, [r12]
0x180027006  mov     r8, r14
0x180027009  mov     [rbp+arg_18], eax
0x18002700c  mov     edx, esi
0x18002700e  mov     rax, [rcx]
0x180027011  mov     cl, [rdi+40h]
0x180027014  mov     [rsp+50h+AccessMode], cl
0x180027018  mov     rcx, rbx
0x18002701b  mov     dword ptr [rsp+50h+ObjectType], r9d
0x180027020  lea     r9, [rbp+arg_18]
0x180027024  call    _guard_dispatch_icall
0x180027029  mov     ebx, eax
0x18002702b  mov     eax, [rbp+arg_18]
0x18002702e  lea     r11, [rsp+50h+var_s0]
0x180027033  mov     rsi, [r11+38h]
0x180027037  mov     [r12], eax
0x18002703b  mov     eax, ebx
0x18002703d  mov     rbx, [r11+30h]
0x180027041  mov     rsp, r11
0x180027044  pop     r15
0x180027046  pop     r14
0x180027048  pop     r12
0x18002704a  pop     rdi
0x18002704b  pop     rbp
0x18002704c  retn
0x18002704e  cmp     byte ptr [rdi+40h], 1
0x180027052  mov     [rbp+BaseAddress], 0
0x18002705a  mov     [rbp+RegionSize], 0
0x180027062  jz      loc_1800271BD
0x180027068  mov     ebx, 0C000000Dh
0x18002706d  jmp     short loc_18002702B
0x18002706f  mov     rcx, [rdi+0B8h]
0x180027076  test    rcx, rcx
0x180027079  jz      short loc_180027068
0x18002707b  mov     edx, [rcx+10h]; Size
0x18002707e  mov     rcx, [rcx+20h]; Src
0x180027082  call    KsecIoctlHandleFunctionReturn
0x180027087  jmp     short loc_180027029
0x180027089  mov     ebx, 0C0000002h
0x18002708e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027095  lea     rax, WPP_GLOBAL_Control
0x18002709c  cmp     rcx, rax
0x18002709f  jz      short loc_18002702B
0x1800270a1  mov     eax, [rcx+2Ch]
0x1800270a4  test    al, 4
0x1800270a6  jz      short loc_18002702B
0x1800270a8  mov     rcx, [rcx+18h]
0x1800270ac  lea     r8, WPP_47798432cc4f3443573e38da5669f213_Traceguids
0x1800270b3  mov     edx, 1Fh
0x1800270b8  call    WPP_SF_D
0x1800270bd  jmp     loc_18002702B
0x1800270c2  lea     rcx, [rbp+RegionSize]; this
0x1800270c6  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x1800270cb  lea     rcx, [rbp+RegionSize]; this
0x1800270cf  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x1800270d4  lea     rcx, [rbp+RegionSize]
0x1800270d8  test    al, al
0x1800270da  jnz     short loc_1800270F6
0x1800270dc  mov     ebx, 0C00002FEh
0x1800270e1  jmp     short loc_1800270EC
0x1800270e3  mov     ebx, 0C0000023h
0x1800270e8  lea     rcx, [rbp+RegionSize]; this
0x1800270ec  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x1800270f1  jmp     loc_18002702B
0x1800270f6  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x1800270fb  cmp     qword ptr [rax], 0
0x1800270ff  jnz     loc_1800271A6
0x180027105  test    r14, r14
0x180027108  jz      short loc_1800270E3
0x18002710a  cmp     dword ptr [r12], 4
0x18002710f  jb      short loc_1800270E3
0x180027111  call    cs:__imp_PsGetCurrentProcess
0x180027118  nop     dword ptr [rax+rax+00h]
0x18002711d  lea     rcx, [rbp+RegionSize]
0x180027121  mov     rdx, rax
0x180027124  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180027129  mov     rcx, rdx; Object
0x18002712c  mov     [rax], rdx
0x18002712f  call    cs:__imp_ObfReferenceObject
0x180027136  nop     dword ptr [rax+rax+00h]
0x18002713b  mov     dl, 1
0x18002713d  mov     cl, dl
0x18002713f  call    CreateClient
0x180027144  lea     rcx, [rbp+RegionSize]
0x180027148  mov     ebx, eax
0x18002714a  test    eax, eax
0x18002714c  js      short loc_1800270EC
0x18002714e  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180027153  mov     r9d, 478h; DesiredAccess
0x180027159  xor     r8d, r8d; PassedAccessState
0x18002715c  mov     edx, 200h; HandleAttributes
0x180027161  lea     rcx, [rax+8]
0x180027165  mov     [rsp+50h+Handle], rcx; Handle
0x18002716a  mov     rcx, [rax]; Object
0x18002716d  mov     [rsp+50h+AccessMode], 0; AccessMode
0x180027172  mov     [rsp+50h+ObjectType], 0; ObjectType
0x18002717b  call    cs:__imp_ObOpenObjectByPointer
0x180027182  nop     dword ptr [rax+rax+00h]
0x180027187  mov     ebx, eax
0x180027189  test    eax, eax
0x18002718b  js      loc_1800270E8
0x180027191  mov     eax, cs:KsecSystemProcessId
0x180027197  mov     [r14], eax
0x18002719a  mov     [rbp+arg_18], 4
0x1800271a1  jmp     loc_1800270E8
0x1800271a6  mov     ebx, 0C00000BBh
0x1800271ab  jmp     loc_1800270E8
0x1800271b0  mov     rcx, rdi; Irp
0x1800271b3  call    IoctlIpcGetQueuedFunctionCalls
0x1800271b8  jmp     loc_180027029
0x1800271bd  test    r15, r15
0x1800271c0  jz      loc_180027068
0x1800271c6  test    rbx, rbx
0x1800271c9  jz      loc_180027068
0x1800271cf  mov     rcx, rdi; Irp
0x1800271d2  call    cs:__imp_IoIs32bitProcess
0x1800271d9  nop     dword ptr [rax+rax+00h]
0x1800271de  test    al, al
0x1800271e0  jz      short loc_1800271EF
0x1800271e2  cmp     esi, 4
0x1800271e5  jnz     loc_180027068
0x1800271eb  mov     edx, [rbx]
0x1800271ed  jmp     short loc_1800271FB
0x1800271ef  cmp     esi, 8
0x1800271f2  jnz     loc_180027068
0x1800271f8  mov     rdx, [rbx]; unsigned __int8 *
0x1800271fb  mov     rcx, r15; struct _EPROCESS *
0x1800271fe  mov     [rbp+BaseAddress], rdx
0x180027202  call    KsecRemoveValidVm
0x180027207  mov     rdi, rax
0x18002720a  test    rax, rax
0x18002720d  jz      loc_180027068
0x180027213  mov     r9d, 8000h; FreeType
0x180027219  mov     [rbp+RegionSize], 0
0x180027221  lea     r8, [rbp+RegionSize]; RegionSize
0x180027225  mov     rcx, rax; ProcessHandle
0x180027228  lea     rdx, [rbp+BaseAddress]; BaseAddress
0x18002722c  call    cs:__imp_ZwFreeVirtualMemory
0x180027233  nop     dword ptr [rax+rax+00h]
0x180027238  mov     rcx, rdi; Handle
0x18002723b  mov     ebx, eax
0x18002723d  call    cs:__imp_ZwClose
0x180027244  nop     dword ptr [rax+rax+00h]
0x180027249  jmp     loc_18002702B
0x18002724e  call    cs:__imp_ExGetPreviousMode
0x180027255  nop     dword ptr [rax+rax+00h]
0x18002725a  test    al, al
0x18002725c  jz      short loc_180027268
0x18002725e  mov     ebx, 0C0000022h
0x180027263  jmp     loc_18002702B
0x180027268  test    rbx, rbx
0x18002726b  jz      loc_180027068
0x180027271  cmp     esi, 10h
0x180027274  jnz     loc_180027068
0x18002727a  mov     rdx, [rbx+8]
0x18002727e  mov     ecx, [rbx]
0x180027280  call    KsecRegisterExtension
0x180027285  jmp     loc_180027029
```
