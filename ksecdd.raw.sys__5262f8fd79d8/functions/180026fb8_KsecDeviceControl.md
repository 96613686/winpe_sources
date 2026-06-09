# KsecDeviceControl

- ea: `0x180026fb8`
- end: `0x1800272da`
- name: `KsecDeviceControl`
- size: `802`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int, _DWORD *, int *, int, PIRP Irp)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180026de0`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x180001f90`
- `0x180002820`
- `0x180005b58`
- `0x180005e94`
- `0x180006bf4`
- `0x180007bd8`
- `0x180010980`
- `0x180022b94`
- `0x1800230d0`
- `0x180026fb8`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x1800271cb`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1800271cb`
- `ntoskrnl!IoGetRequestorProcess` at `0x180026fea`
- `ntoskrnl!IoGetRequestorProcess` at `0x180026fea`
- `ntoskrnl!ObfReferenceObject` at `0x18002717f`
- `ntoskrnl!ObfReferenceObject` at `0x18002717f`
- `ntoskrnl!ExGetPreviousMode` at `0x18002729e`
- `ntoskrnl!ExGetPreviousMode` at `0x18002729e`
- `ntoskrnl!IoIs32bitProcess` at `0x180027222`
- `ntoskrnl!IoIs32bitProcess` at `0x180027222`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x18002727c`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x18002727c`
- `ntoskrnl!PsGetCurrentProcess` at `0x180027161`
- `ntoskrnl!PsGetCurrentProcess` at `0x180027161`
- `ntoskrnl!ZwClose` at `0x18002728d`
- `ntoskrnl!ZwClose` at `0x18002728d`

## pseudocode

```c
__int64 __fastcall KsecDeviceControl(unsigned int *a1, unsigned int a2, _DWORD *a3, unsigned int *a4, int a5, PIRP Irp)
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
  PVOID *v24; // rax
  void *v25; // rdx
  void *v26; // rax
  void *v27; // rdi
  ULONG_PTR RegionSize; // [rsp+40h] [rbp-10h] BYREF
  PVOID BaseAddress; // [rsp+48h] [rbp-8h] BYREF
  int v30; // [rsp+98h] [rbp+48h] BYREF

  v6 = Irp;
  v30 = 0;
  RequestorProcess = IoGetRequestorProcess(Irp);
  v12 = RequestorProcess;
  switch ( a5 )
  {
    case 3735608:
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
    case 3735640:
      v16 = v6->RequestorMode == 1;
      BaseAddress = 0;
      RegionSize = 0;
      if ( !v16 || !RequestorProcess || !a1 )
        goto LABEL_12;
      if ( IoIs32bitProcess(v6) )
      {
        if ( a2 != 4 )
          goto LABEL_12;
        v25 = (void *)*a1;
      }
      else
      {
        if ( a2 != 8 )
          goto LABEL_12;
        v25 = *(void **)a1;
      }
      BaseAddress = v25;
      v26 = (void *)KsecRemoveValidVm(v12, (unsigned __int8 *)v25);
      v27 = v26;
      if ( v26 )
      {
        RegionSize = 0;
        Client = ZwFreeVirtualMemory(v26, &BaseAddress, &RegionSize, 0x8000u);
        ZwClose(v27);
        break;
      }
      goto LABEL_12;
    case 3735658:
      QueuedFunctionCalls = IoctlIpcGetQueuedFunctionCalls(v6);
      goto LABEL_9;
    case 3735663:
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
    case 3768320:
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
          Client = CreateClient(1, 1);
          if ( Client >= 0 )
          {
            v24 = (PVOID *)KsecddLsaStateRef::operator _KSECDDLSASTATE *(&RegionSize);
            Client = ObOpenObjectByPointer(*v24, 0x200u, 0, 0x478u, 0, 0, v24 + 1);
            if ( Client >= 0 )
            {
              *a3 = KsecSystemProcessId;
              v30 = 4;
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
      if ( WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink && WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink->Flink )
      {
        v30 = *a4;
        QueuedFunctionCalls = ((__int64 (__fastcall *)(unsigned int *, _QWORD, _DWORD *, int *, int, KPROCESSOR_MODE))WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink->Flink)(
                                a1,
                                a2,
                                a3,
                                &v30,
                                a5,
                                v6->RequestorMode);
LABEL_9:
        Client = QueuedFunctionCalls;
        break;
      }
      Client = -1073741822;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 31, &WPP_47798432cc4f3443573e38da5669f213_Traceguids);
      break;
  }
  *a4 = v30;
  return (unsigned int)Client;
}

```

## disassembly

```asm
0x180026fb8  mov     [rsp-28h+arg_0], rbx
0x180026fbd  mov     [rsp-28h+arg_8], rsi
0x180026fc2  push    rbp
0x180026fc3  push    rdi
0x180026fc4  push    r12
0x180026fc6  push    r14
0x180026fc8  push    r15
0x180026fca  mov     rbp, rsp
0x180026fcd  sub     rsp, 50h
0x180026fd1  mov     rdi, [rbp+Irp]
0x180026fd5  mov     rbx, rcx
0x180026fd8  mov     rcx, rdi; Irp
0x180026fdb  mov     [rbp+arg_18], 0
0x180026fe2  mov     r12, r9
0x180026fe5  mov     r14, r8
0x180026fe8  mov     esi, edx
0x180026fea  call    cs:__imp_IoGetRequestorProcess
0x180026ff1  nop     dword ptr [rax+rax+00h]
0x180026ff6  mov     r9d, [rbp+arg_20]
0x180026ffa  mov     r10d, r9d
0x180026ffd  mov     r15, rax
0x180027000  sub     r10d, 390038h
0x180027007  jz      loc_18002729E
0x18002700d  sub     r10d, 20h ; ' '
0x180027011  jz      loc_18002709E
0x180027017  sub     r10d, 12h
0x18002701b  jz      loc_180027200
0x180027021  sub     r10d, 5
0x180027025  jz      loc_1800270BF
0x18002702b  cmp     r10d, 7F91h
0x180027032  jz      loc_180027112
0x180027038  mov     rcx, cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink
0x18002703f  test    rcx, rcx
0x180027042  jz      loc_1800270D9
0x180027048  cmp     qword ptr [rcx], 0
0x18002704c  jz      loc_1800270D9
0x180027052  mov     eax, [r12]
0x180027056  mov     r8, r14
0x180027059  mov     [rbp+arg_18], eax
0x18002705c  mov     edx, esi
0x18002705e  mov     rax, [rcx]
0x180027061  mov     cl, [rdi+40h]
0x180027064  mov     [rsp+50h+AccessMode], cl
0x180027068  mov     rcx, rbx
0x18002706b  mov     dword ptr [rsp+50h+ObjectType], r9d
0x180027070  lea     r9, [rbp+arg_18]
0x180027074  call    _guard_dispatch_icall
0x180027079  mov     ebx, eax
0x18002707b  mov     eax, [rbp+arg_18]
0x18002707e  lea     r11, [rsp+50h+var_s0]
0x180027083  mov     rsi, [r11+38h]
0x180027087  mov     [r12], eax
0x18002708b  mov     eax, ebx
0x18002708d  mov     rbx, [r11+30h]
0x180027091  mov     rsp, r11
0x180027094  pop     r15
0x180027096  pop     r14
0x180027098  pop     r12
0x18002709a  pop     rdi
0x18002709b  pop     rbp
0x18002709c  retn
0x18002709e  cmp     byte ptr [rdi+40h], 1
0x1800270a2  mov     [rbp+BaseAddress], 0
0x1800270aa  mov     [rbp+RegionSize], 0
0x1800270b2  jz      loc_18002720D
0x1800270b8  mov     ebx, 0C000000Dh
0x1800270bd  jmp     short loc_18002707B
0x1800270bf  mov     rcx, [rdi+0B8h]
0x1800270c6  test    rcx, rcx
0x1800270c9  jz      short loc_1800270B8
0x1800270cb  mov     edx, [rcx+10h]; Size
0x1800270ce  mov     rcx, [rcx+20h]; Src
0x1800270d2  call    KsecIoctlHandleFunctionReturn
0x1800270d7  jmp     short loc_180027079
0x1800270d9  mov     ebx, 0C0000002h
0x1800270de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800270e5  lea     rax, WPP_GLOBAL_Control
0x1800270ec  cmp     rcx, rax
0x1800270ef  jz      short loc_18002707B
0x1800270f1  mov     eax, [rcx+2Ch]
0x1800270f4  test    al, 4
0x1800270f6  jz      short loc_18002707B
0x1800270f8  mov     rcx, [rcx+18h]
0x1800270fc  lea     r8, WPP_47798432cc4f3443573e38da5669f213_Traceguids
0x180027103  mov     edx, 1Fh
0x180027108  call    WPP_SF_D
0x18002710d  jmp     loc_18002707B
0x180027112  lea     rcx, [rbp+RegionSize]; this
0x180027116  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x18002711b  lea     rcx, [rbp+RegionSize]; this
0x18002711f  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x180027124  lea     rcx, [rbp+RegionSize]
0x180027128  test    al, al
0x18002712a  jnz     short loc_180027146
0x18002712c  mov     ebx, 0C00002FEh
0x180027131  jmp     short loc_18002713C
0x180027133  mov     ebx, 0C0000023h
0x180027138  lea     rcx, [rbp+RegionSize]; this
0x18002713c  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180027141  jmp     loc_18002707B
0x180027146  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x18002714b  cmp     qword ptr [rax], 0
0x18002714f  jnz     loc_1800271F6
0x180027155  test    r14, r14
0x180027158  jz      short loc_180027133
0x18002715a  cmp     dword ptr [r12], 4
0x18002715f  jb      short loc_180027133
0x180027161  call    cs:__imp_PsGetCurrentProcess
0x180027168  nop     dword ptr [rax+rax+00h]
0x18002716d  lea     rcx, [rbp+RegionSize]
0x180027171  mov     rdx, rax
0x180027174  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180027179  mov     rcx, rdx; Object
0x18002717c  mov     [rax], rdx
0x18002717f  call    cs:__imp_ObfReferenceObject
0x180027186  nop     dword ptr [rax+rax+00h]
0x18002718b  mov     dl, 1
0x18002718d  mov     cl, dl
0x18002718f  call    CreateClient
0x180027194  lea     rcx, [rbp+RegionSize]
0x180027198  mov     ebx, eax
0x18002719a  test    eax, eax
0x18002719c  js      short loc_18002713C
0x18002719e  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x1800271a3  mov     r9d, 478h; DesiredAccess
0x1800271a9  xor     r8d, r8d; PassedAccessState
0x1800271ac  mov     edx, 200h; HandleAttributes
0x1800271b1  lea     rcx, [rax+8]
0x1800271b5  mov     [rsp+50h+Handle], rcx; Handle
0x1800271ba  mov     rcx, [rax]; Object
0x1800271bd  mov     [rsp+50h+AccessMode], 0; AccessMode
0x1800271c2  mov     [rsp+50h+ObjectType], 0; ObjectType
0x1800271cb  call    cs:__imp_ObOpenObjectByPointer
0x1800271d2  nop     dword ptr [rax+rax+00h]
0x1800271d7  mov     ebx, eax
0x1800271d9  test    eax, eax
0x1800271db  js      loc_180027138
0x1800271e1  mov     eax, cs:KsecSystemProcessId
0x1800271e7  mov     [r14], eax
0x1800271ea  mov     [rbp+arg_18], 4
0x1800271f1  jmp     loc_180027138
0x1800271f6  mov     ebx, 0C00000BBh
0x1800271fb  jmp     loc_180027138
0x180027200  mov     rcx, rdi; Irp
0x180027203  call    IoctlIpcGetQueuedFunctionCalls
0x180027208  jmp     loc_180027079
0x18002720d  test    r15, r15
0x180027210  jz      loc_1800270B8
0x180027216  test    rbx, rbx
0x180027219  jz      loc_1800270B8
0x18002721f  mov     rcx, rdi; Irp
0x180027222  call    cs:__imp_IoIs32bitProcess
0x180027229  nop     dword ptr [rax+rax+00h]
0x18002722e  test    al, al
0x180027230  jz      short loc_18002723F
0x180027232  cmp     esi, 4
0x180027235  jnz     loc_1800270B8
0x18002723b  mov     edx, [rbx]
0x18002723d  jmp     short loc_18002724B
0x18002723f  cmp     esi, 8
0x180027242  jnz     loc_1800270B8
0x180027248  mov     rdx, [rbx]; unsigned __int8 *
0x18002724b  mov     rcx, r15; struct _EPROCESS *
0x18002724e  mov     [rbp+BaseAddress], rdx
0x180027252  call    KsecRemoveValidVm
0x180027257  mov     rdi, rax
0x18002725a  test    rax, rax
0x18002725d  jz      loc_1800270B8
0x180027263  mov     r9d, 8000h; FreeType
0x180027269  mov     [rbp+RegionSize], 0
0x180027271  lea     r8, [rbp+RegionSize]; RegionSize
0x180027275  mov     rcx, rax; ProcessHandle
0x180027278  lea     rdx, [rbp+BaseAddress]; BaseAddress
0x18002727c  call    cs:__imp_ZwFreeVirtualMemory
0x180027283  nop     dword ptr [rax+rax+00h]
0x180027288  mov     rcx, rdi; Handle
0x18002728b  mov     ebx, eax
0x18002728d  call    cs:__imp_ZwClose
0x180027294  nop     dword ptr [rax+rax+00h]
0x180027299  jmp     loc_18002707B
0x18002729e  call    cs:__imp_ExGetPreviousMode
0x1800272a5  nop     dword ptr [rax+rax+00h]
0x1800272aa  test    al, al
0x1800272ac  jz      short loc_1800272B8
0x1800272ae  mov     ebx, 0C0000022h
0x1800272b3  jmp     loc_18002707B
0x1800272b8  test    rbx, rbx
0x1800272bb  jz      loc_1800270B8
0x1800272c1  cmp     esi, 10h
0x1800272c4  jnz     loc_1800270B8
0x1800272ca  mov     rdx, [rbx+8]
0x1800272ce  mov     ecx, [rbx]
0x1800272d0  call    KsecRegisterExtension
0x1800272d5  jmp     loc_180027079
```
