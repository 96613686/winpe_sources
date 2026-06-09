# RefsCheckpointForVolumeSnapshot

- ea: `0x1c01cd36c`
- end: `0x1c01cd859`
- name: `RefsCheckpointForVolumeSnapshot`
- size: `1261`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1c0196bc8`

## callees

- `0x1c000f770`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c00b1c2c`
- `0x1c015527c`
- `0x1c0163360`
- `0x1c016d3c4`
- `0x1c01c42bc`
- `0x1c01c47c8`
- `0x1c01cd36c`
- `0x1c01cd860`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c01cd756`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01cd80f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01cd756`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01cd80f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01cd54d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01cd54d`
- `ntoskrnl!ZwClose` at `0x1c01cd790`
- `ntoskrnl!ZwClose` at `0x1c01cd844`
- `ntoskrnl!ZwClose` at `0x1c01cd790`
- `ntoskrnl!ZwClose` at `0x1c01cd844`
- `ntoskrnl!ZwOpenEvent` at `0x1c01cd5a5`
- `ntoskrnl!ZwOpenEvent` at `0x1c01cd5a5`
- `ntoskrnl!KeSetPriorityThread` at `0x1c01cd5fe`
- `ntoskrnl!KeSetPriorityThread` at `0x1c01cd776`
- `ntoskrnl!KeSetPriorityThread` at `0x1c01cd82e`
- `ntoskrnl!KeSetPriorityThread` at `0x1c01cd5fe`
- `ntoskrnl!KeSetPriorityThread` at `0x1c01cd776`
- `ntoskrnl!KeSetPriorityThread` at `0x1c01cd82e`

## pseudocode

```c
__int64 __fastcall RefsCheckpointForVolumeSnapshot(__int64 a1, _BYTE *a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rdi
  NTSTATUS v8; // ebx
  NTSTATUS v9; // eax
  int v10; // r8d
  bool v11; // [rsp+50h] [rbp-128h]
  char v12; // [rsp+51h] [rbp-127h]
  _BYTE v13[2]; // [rsp+52h] [rbp-126h] BYREF
  NTSTATUS v14; // [rsp+54h] [rbp-124h]
  int v15; // [rsp+58h] [rbp-120h]
  KPRIORITY Priority; // [rsp+5Ch] [rbp-11Ch]
  int v17; // [rsp+60h] [rbp-118h]
  __int64 v18; // [rsp+68h] [rbp-110h] BYREF
  void *EventHandle[4]; // [rsp+70h] [rbp-108h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-E8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-D8h] BYREF
  WCHAR SourceString[56]; // [rsp+D0h] [rbp-A8h] BYREF

  EventHandle[1] = (void *)a1;
  EventHandle[3] = a2;
  v15 = 0;
  v17 = 0;
  v14 = 0;
  Priority = 0;
  v11 = 0;
  v12 = 0;
  v13[0] = 0;
  wcscpy(SourceString, L"\\BaseNamedObjects\\Microsoft.ReFS.LeakDetection.Event.X");
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  EventHandle[0] = 0;
  v18 = 0;
  v6 = *(_QWORD *)(a1 + 64);
  EventHandle[2] = (void *)v6;
  if ( (*(_DWORD *)(v6 + 4) & 0x2000000) != 0 )
    return 0;
  LOBYTE(a3) = 1;
  RefsAcquireExclusiveVcb(a1, v6, a3, a4);
  v17 = 1;
  *a2 = 0;
  if ( (*(_DWORD *)(v6 + 4) & 1) == 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v8 = -1073741202;
    }
    else
    {
      v8 = -1073741202;
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_19f529de63163e1eb7d47934ee167ea0_Traceguids, 3221226094LL);
    }
    if ( !RefsStatusDebugEnabled )
      goto LABEL_11;
    goto LABEL_10;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = ZwOpenEvent(EventHandle, 0x1F0003u, &ObjectAttributes);
  v8 = v9;
  v14 = v9;
  if ( v9 < 0 )
  {
    if ( v9 == -1073741766 || v9 == -1073741772 )
    {
      v8 = 0;
      v14 = 0;
    }
  }
  else
  {
    v12 = 1;
  }
  if ( v8 < 0 )
    goto LABEL_28;
  RefsFlushVolume(a1, v6, 65);
  Priority = KeSetPriorityThread(KeGetCurrentThread(), 16);
  v11 = Priority != 16;
  RefsAcquireAllFiles(a1, v6, 63, &v18);
  v15 = 1;
  RefsFlushVolume(a1, v6, 1730);
  *(_DWORD *)(a1 + 224) = 10;
  LOBYTE(v10) = 1;
  RefsCheckpointVolume(a1, v6, v10, 0, 1, 0, 0, (__int64)a2, (__int64)v13);
  RefsCommitCurrentTransaction(a1, 0);
  if ( !v12 || v13[0] )
  {
    RefsReleaseAllFiles(a1, v6, 24, v18);
    v18 = 0;
    v8 = v14;
    goto LABEL_28;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v8 = -1073740761;
  }
  else
  {
    v8 = -1073740761;
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_19f529de63163e1eb7d47934ee167ea0_Traceguids, 3221226535LL);
  }
  if ( RefsStatusDebugEnabled )
LABEL_10:
    RefsStatusDebug(v8);
LABEL_11:
  v14 = v8;
LABEL_28:
  if ( v8 < 0 )
  {
    if ( *a2 )
    {
      MsEnableCheckpointingForSnapshot(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 104LL));
      *a2 = 0;
    }
    if ( v15 )
      RefsReleaseAllFiles(a1, v6, 62, v18);
    ExReleaseResourceLite((PERESOURCE)(v6 + 1424));
  }
  if ( v11 )
  {
    KeSetPriorityThread(KeGetCurrentThread(), Priority);
    v8 = v14;
  }
  if ( EventHandle[0] )
    ZwClose(EventHandle[0]);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1c01cd36c  mov     r11, rsp
0x1c01cd36f  mov     [r11+18h], rbx
0x1c01cd373  push    rsi
0x1c01cd374  push    rdi
0x1c01cd375  push    r12
0x1c01cd377  push    r14
0x1c01cd379  push    r15
0x1c01cd37b  sub     rsp, 150h
0x1c01cd382  mov     rax, cs:__security_cookie
0x1c01cd389  xor     rax, rsp
0x1c01cd38c  mov     [rsp+178h+var_38], rax
0x1c01cd394  mov     r14, rdx
0x1c01cd397  mov     rsi, rcx
0x1c01cd39a  mov     [rsp+178h+var_100], rcx
0x1c01cd39f  mov     [rsp+178h+var_F0], rdx
0x1c01cd3a7  xor     r15d, r15d
0x1c01cd3aa  mov     [rsp+178h+var_120], r15d
0x1c01cd3af  mov     [rsp+178h+var_118], r15d
0x1c01cd3b4  mov     [rsp+178h+var_124], r15d
0x1c01cd3b9  mov     [rsp+178h+Priority], r15d
0x1c01cd3be  mov     [rsp+178h+var_128], r15b
0x1c01cd3c3  mov     [rsp+178h+var_127], r15b
0x1c01cd3c8  mov     [rsp+178h+var_126], r15b
0x1c01cd3cd  movaps  xmm0, xmmword ptr cs:aBasenamedobjec; "\\BaseNamedObjects\\Microsoft.ReFS.Leak"...
0x1c01cd3d4  movaps  xmmword ptr [rsp+178h+SourceString], xmm0
0x1c01cd3dc  movaps  xmm1, xmmword ptr cs:aBasenamedobjec+10h; "edObjects\\Microsoft.ReFS.LeakDetection"...
0x1c01cd3e3  movaps  [rsp+178h+var_98], xmm1
0x1c01cd3eb  movaps  xmm0, xmmword ptr cs:aBasenamedobjec+20h; "s\\Microsoft.ReFS.LeakDetection.Event.X"
0x1c01cd3f2  movaps  [rsp+178h+var_88], xmm0
0x1c01cd3fa  movaps  xmm1, xmmword ptr cs:aBasenamedobjec+30h; "oft.ReFS.LeakDetection.Event.X"
0x1c01cd401  movaps  xmmword ptr [r11-78h], xmm1
0x1c01cd406  movaps  xmm0, xmmword ptr cs:aBasenamedobjec+40h; ".LeakDetection.Event.X"
0x1c01cd40d  movaps  xmmword ptr [r11-68h], xmm0
0x1c01cd412  movaps  xmm1, xmmword ptr cs:aBasenamedobjec+50h; "ection.Event.X"
0x1c01cd419  movaps  xmmword ptr [r11-58h], xmm1
0x1c01cd41e  movsd   xmm0, qword ptr cs:aBasenamedobjec+60h; "vent.X"
0x1c01cd426  movsd   qword ptr [r11-48h], xmm0
0x1c01cd42c  mov     eax, dword ptr cs:aBasenamedobjec+68h; ".X"
0x1c01cd432  mov     [r11-40h], eax
0x1c01cd436  movzx   eax, word ptr cs:aBasenamedobjec+6Ch; ""
0x1c01cd43d  mov     [r11-3Ch], ax
0x1c01cd442  xorps   xmm0, xmm0
0x1c01cd445  movups  xmmword ptr [rsp+178h+ObjectAttributes.Length], xmm0
0x1c01cd44d  movups  xmmword ptr [rsp+178h+ObjectAttributes.ObjectName], xmm0
0x1c01cd455  movups  xmmword ptr [rsp+178h+ObjectAttributes.SecurityDescriptor], xmm0
0x1c01cd45d  movups  xmmword ptr [rsp+178h+DestinationString.Length], xmm0
0x1c01cd465  mov     [rsp+178h+EventHandle], r15
0x1c01cd46a  mov     [rsp+178h+var_110], r15
0x1c01cd46f  mov     rdi, [rcx+40h]
0x1c01cd473  mov     [rsp+178h+var_F8], rdi
0x1c01cd47b  mov     eax, [rdi+4]
0x1c01cd47e  bt      eax, 19h
0x1c01cd482  jnb     short loc_1C01CD4AF
0x1c01cd484  xor     eax, eax
0x1c01cd486  mov     rcx, [rsp+178h+var_38]
0x1c01cd48e  xor     rcx, rsp; StackCookie
0x1c01cd491  call    __security_check_cookie
0x1c01cd496  mov     rbx, [rsp+178h+arg_10]
0x1c01cd49e  add     rsp, 150h
0x1c01cd4a5  pop     r15
0x1c01cd4a7  pop     r14
0x1c01cd4a9  pop     r12
0x1c01cd4ab  pop     rdi
0x1c01cd4ac  pop     rsi
0x1c01cd4ad  retn
0x1c01cd4af  mov     r12d, 1
0x1c01cd4b5  mov     r8b, r12b
0x1c01cd4b8  mov     rdx, rdi
0x1c01cd4bb  call    RefsAcquireExclusiveVcb
0x1c01cd4c0  mov     [rsp+178h+var_118], r12d
0x1c01cd4c5  mov     [r14], r15b
0x1c01cd4c8  mov     eax, [rdi+4]
0x1c01cd4cb  test    r12b, al
0x1c01cd4ce  jnz     short loc_1C01CD53D
0x1c01cd4d0  lea     rax, WPP_GLOBAL_Control
0x1c01cd4d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01cd4de  cmp     rcx, rax
0x1c01cd4e1  jz      short loc_1C01CD511
0x1c01cd4e3  mov     eax, [rcx+2Ch]
0x1c01cd4e6  bt      eax, 8
0x1c01cd4ea  jnb     short loc_1C01CD511
0x1c01cd4ec  cmp     byte ptr [rcx+29h], 4
0x1c01cd4f0  jb      short loc_1C01CD511
0x1c01cd4f2  lea     edx, [r12+0Fh]
0x1c01cd4f7  mov     ebx, 0C000026Eh
0x1c01cd4fc  mov     r9d, ebx
0x1c01cd4ff  lea     r8, WPP_19f529de63163e1eb7d47934ee167ea0_Traceguids
0x1c01cd506  mov     rcx, [rcx+18h]
0x1c01cd50a  call    WPP_SF_D
0x1c01cd50f  jmp     short loc_1C01CD516
0x1c01cd511  mov     ebx, 0C000026Eh
0x1c01cd516  mov     al, cs:RefsStatusDebugEnabled
0x1c01cd51c  test    al, al
0x1c01cd51e  jz      short loc_1C01CD534
0x1c01cd520  mov     r8d, 259h
0x1c01cd526  lea     rdx, aTranssupC; "TransSup.c"
0x1c01cd52d  mov     ecx, ebx; Status
0x1c01cd52f  call    RefsStatusDebug
0x1c01cd534  mov     [rsp+178h+var_124], ebx
0x1c01cd538  jmp     loc_1C01CD719
0x1c01cd53d  lea     rdx, [rsp+178h+SourceString]; SourceString
0x1c01cd545  lea     rcx, [rsp+178h+DestinationString]; DestinationString
0x1c01cd54d  call    cs:__imp_RtlInitUnicodeString
0x1c01cd554  nop     dword ptr [rax+rax+00h]
0x1c01cd559  mov     [rsp+178h+ObjectAttributes.Length], 30h ; '0'
0x1c01cd564  mov     [rsp+178h+ObjectAttributes.RootDirectory], r15
0x1c01cd56c  mov     [rsp+178h+ObjectAttributes.Attributes], 200h
0x1c01cd577  lea     rax, [rsp+178h+DestinationString]
0x1c01cd57f  mov     [rsp+178h+ObjectAttributes.ObjectName], rax
0x1c01cd587  xorps   xmm0, xmm0
0x1c01cd58a  movdqu  xmmword ptr [rsp+178h+ObjectAttributes.SecurityDescriptor], xmm0
0x1c01cd593  lea     r8, [rsp+178h+ObjectAttributes]; ObjectAttributes
0x1c01cd59b  mov     edx, 1F0003h; DesiredAccess
0x1c01cd5a0  lea     rcx, [rsp+178h+EventHandle]; EventHandle
0x1c01cd5a5  call    cs:__imp_ZwOpenEvent
0x1c01cd5ac  nop     dword ptr [rax+rax+00h]
0x1c01cd5b1  mov     ebx, eax
0x1c01cd5b3  mov     [rsp+178h+var_124], eax
0x1c01cd5b7  test    eax, eax
0x1c01cd5b9  js      short loc_1C01CD5C2
0x1c01cd5bb  mov     [rsp+178h+var_127], r12b
0x1c01cd5c0  jmp     short loc_1C01CD5D7
0x1c01cd5c2  cmp     eax, 0C000003Ah
0x1c01cd5c7  jz      short loc_1C01CD5D0
0x1c01cd5c9  cmp     eax, 0C0000034h
0x1c01cd5ce  jnz     short loc_1C01CD5D7
0x1c01cd5d0  mov     ebx, r15d
0x1c01cd5d3  mov     [rsp+178h+var_124], ebx
0x1c01cd5d7  test    ebx, ebx
0x1c01cd5d9  js      loc_1C01CD719
0x1c01cd5df  mov     r8d, 41h ; 'A'
0x1c01cd5e5  mov     rdx, rdi
0x1c01cd5e8  mov     rcx, rsi
0x1c01cd5eb  call    RefsFlushVolume
0x1c01cd5f0  mov     rcx, gs:188h; Thread
0x1c01cd5f9  mov     edx, 10h; Priority
0x1c01cd5fe  call    cs:__imp_KeSetPriorityThread
0x1c01cd605  nop     dword ptr [rax+rax+00h]
0x1c01cd60a  mov     [rsp+178h+Priority], eax
0x1c01cd60e  movzx   ecx, [rsp+178h+var_128]
0x1c01cd613  cmp     eax, 10h
0x1c01cd616  cmovnz  ecx, r12d
0x1c01cd61a  mov     [rsp+178h+var_128], cl
0x1c01cd61e  lea     r9, [rsp+178h+var_110]
0x1c01cd623  mov     r8d, 3Fh ; '?'
0x1c01cd629  mov     rdx, rdi
0x1c01cd62c  mov     rcx, rsi
0x1c01cd62f  call    RefsAcquireAllFiles
0x1c01cd634  mov     [rsp+178h+var_120], r12d
0x1c01cd639  mov     r8d, 6C2h
0x1c01cd63f  mov     rdx, rdi
0x1c01cd642  mov     rcx, rsi
0x1c01cd645  call    RefsFlushVolume
0x1c01cd64a  mov     dword ptr [rsi+0E0h], 0Ah
0x1c01cd654  lea     rax, [rsp+178h+var_126]
0x1c01cd659  mov     [rsp+178h+var_138], rax
0x1c01cd65e  mov     [rsp+178h+var_140], r14
0x1c01cd663  mov     [rsp+178h+var_148], r15b
0x1c01cd668  mov     [rsp+178h+var_150], r15b
0x1c01cd66d  mov     [rsp+178h+var_158], r12b
0x1c01cd672  xor     r9d, r9d
0x1c01cd675  mov     r8b, r12b
0x1c01cd678  mov     rdx, rdi
0x1c01cd67b  mov     rcx, rsi
0x1c01cd67e  call    RefsCheckpointVolume
0x1c01cd683  xor     edx, edx
0x1c01cd685  mov     rcx, rsi
0x1c01cd688  call    RefsCommitCurrentTransaction
0x1c01cd68d  cmp     [rsp+178h+var_127], r15b
0x1c01cd692  jz      short loc_1C01CD6FA
0x1c01cd694  cmp     [rsp+178h+var_126], r15b
0x1c01cd699  jnz     short loc_1C01CD6FA
0x1c01cd69b  lea     rax, WPP_GLOBAL_Control
0x1c01cd6a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01cd6a9  cmp     rcx, rax
0x1c01cd6ac  jz      short loc_1C01CD6DC
0x1c01cd6ae  mov     eax, [rcx+2Ch]
0x1c01cd6b1  bt      eax, 8
0x1c01cd6b5  jnb     short loc_1C01CD6DC
0x1c01cd6b7  cmp     byte ptr [rcx+29h], 4
0x1c01cd6bb  jb      short loc_1C01CD6DC
0x1c01cd6bd  mov     edx, 11h
0x1c01cd6c2  mov     ebx, 0C0000427h
0x1c01cd6c7  mov     r9d, ebx
0x1c01cd6ca  lea     r8, WPP_19f529de63163e1eb7d47934ee167ea0_Traceguids
0x1c01cd6d1  mov     rcx, [rcx+18h]
0x1c01cd6d5  call    WPP_SF_D
0x1c01cd6da  jmp     short loc_1C01CD6E1
0x1c01cd6dc  mov     ebx, 0C0000427h
0x1c01cd6e1  mov     al, cs:RefsStatusDebugEnabled
0x1c01cd6e7  test    al, al
0x1c01cd6e9  jz      loc_1C01CD534
0x1c01cd6ef  mov     r8d, 2B7h
0x1c01cd6f5  jmp     loc_1C01CD526
0x1c01cd6fa  mov     r9, [rsp+178h+var_110]
0x1c01cd6ff  mov     r8d, 18h
0x1c01cd705  mov     rdx, rdi
0x1c01cd708  mov     rcx, rsi
0x1c01cd70b  call    RefsReleaseAllFiles
0x1c01cd710  mov     [rsp+178h+var_110], r15
0x1c01cd715  mov     ebx, [rsp+178h+var_124]
0x1c01cd719  test    ebx, ebx
0x1c01cd71b  jns     short loc_1C01CD762
0x1c01cd71d  cmp     [r14], r15b
0x1c01cd720  jz      short loc_1C01CD732
0x1c01cd722  mov     rcx, [rsi+40h]
0x1c01cd726  mov     rcx, [rcx+68h]
0x1c01cd72a  call    MsEnableCheckpointingForSnapshot
0x1c01cd72f  mov     [r14], r15b
0x1c01cd732  cmp     [rsp+178h+var_120], r15d
0x1c01cd737  jz      short loc_1C01CD74F
0x1c01cd739  mov     r9, [rsp+178h+var_110]
0x1c01cd73e  mov     r8d, 3Eh ; '>'
0x1c01cd744  mov     rdx, rdi
0x1c01cd747  mov     rcx, rsi
0x1c01cd74a  call    RefsReleaseAllFiles
0x1c01cd74f  lea     rcx, [rdi+590h]; Resource
0x1c01cd756  call    cs:__imp_ExReleaseResourceLite
0x1c01cd75d  nop     dword ptr [rax+rax+00h]
0x1c01cd762  cmp     [rsp+178h+var_128], r15b
0x1c01cd767  jz      short loc_1C01CD786
0x1c01cd769  mov     rcx, gs:188h; Thread
0x1c01cd772  mov     edx, [rsp+178h+Priority]; Priority
0x1c01cd776  call    cs:__imp_KeSetPriorityThread
0x1c01cd77d  nop     dword ptr [rax+rax+00h]
0x1c01cd782  mov     ebx, [rsp+178h+var_124]
0x1c01cd786  mov     rcx, [rsp+178h+EventHandle]; Handle
0x1c01cd78b  test    rcx, rcx
0x1c01cd78e  jz      short loc_1C01CD79C
0x1c01cd790  call    cs:__imp_ZwClose
0x1c01cd797  nop     dword ptr [rax+rax+00h]
0x1c01cd79c  mov     eax, ebx
0x1c01cd79e  jmp     loc_1C01CD486
0x1c01cd7a3  push    rbx
0x1c01cd7a5  push    rbp
0x1c01cd7a6  sub     rsp, 58h
0x1c01cd7aa  mov     rbp, rdx
0x1c01cd7ad  cmp     dword ptr [rbp+54h], 0
0x1c01cd7b1  jl      short loc_1C01CD7BA
0x1c01cd7b3  movzx   eax, cl
0x1c01cd7b6  test    cl, cl
0x1c01cd7b8  jz      short loc_1C01CD81C
0x1c01cd7ba  mov     rbx, [rbp+88h]
0x1c01cd7c1  cmp     byte ptr [rbx], 0
0x1c01cd7c4  jz      short loc_1C01CD7DA
0x1c01cd7c6  mov     rax, [rbp+78h]
0x1c01cd7ca  mov     rcx, [rax+40h]
0x1c01cd7ce  mov     rcx, [rcx+68h]
0x1c01cd7d2  call    MsEnableCheckpointingForSnapshot
0x1c01cd7d7  mov     byte ptr [rbx], 0
0x1c01cd7da  cmp     dword ptr [rbp+58h], 0
0x1c01cd7de  jz      short loc_1C01CD7FB
0x1c01cd7e0  mov     r9, [rbp+68h]
0x1c01cd7e4  mov     r8d, 3Eh ; '>'
0x1c01cd7ea  mov     rdx, [rbp+80h]
0x1c01cd7f1  mov     rcx, [rbp+78h]
0x1c01cd7f5  call    RefsReleaseAllFiles
0x1c01cd7fa  nop
0x1c01cd7fb  cmp     dword ptr [rbp+60h], 0
0x1c01cd7ff  jz      short loc_1C01CD81C
0x1c01cd801  mov     rcx, [rbp+80h]
0x1c01cd808  add     rcx, 590h; Resource
0x1c01cd80f  call    cs:__imp_ExReleaseResourceLite
0x1c01cd816  nop     dword ptr [rax+rax+00h]
0x1c01cd81b  nop
0x1c01cd81c  cmp     byte ptr [rbp+50h], 0
0x1c01cd820  jz      short loc_1C01CD83B
0x1c01cd822  mov     rcx, gs:188h; Thread
0x1c01cd82b  mov     edx, [rbp+5Ch]; Priority
0x1c01cd82e  call    cs:__imp_KeSetPriorityThread
0x1c01cd835  nop     dword ptr [rax+rax+00h]
0x1c01cd83a  nop
0x1c01cd83b  mov     rcx, [rbp+70h]; Handle
0x1c01cd83f  test    rcx, rcx
0x1c01cd842  jz      short loc_1C01CD851
0x1c01cd844  call    cs:__imp_ZwClose
0x1c01cd84b  nop     dword ptr [rax+rax+00h]
0x1c01cd850  nop
0x1c01cd851  add     rsp, 58h
0x1c01cd855  pop     rbp
0x1c01cd856  pop     rbx
0x1c01cd857  retn
```
