# RefsAddToNewThread

- ea: `0x1c00aa528`
- end: `0x1c00aa64c`
- name: `RefsAddToNewThread`
- size: `292`
- prototype: `__int64 __fastcall(PVOID StartContext)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c00592b0`

## callees

- `0x1c000f770`
- `0x1c0013f90`
- `0x1c00aa528`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x1c00aa570`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c00aa570`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1c00aa55a`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1c00aa55a`
- `ntoskrnl!ZwClose` at `0x1c00aa5ff`
- `ntoskrnl!ZwClose` at `0x1c00aa5ff`
- `ntoskrnl!PsCreateSystemThread` at `0x1c00aa5e5`
- `ntoskrnl!PsCreateSystemThread` at `0x1c00aa5e5`

## pseudocode

```c
NTSTATUS __fastcall RefsAddToNewThread(char *StartContext, __int64 a2)
{
  char *v4; // rbx
  int ActivityIdIrp; // eax
  char *v6; // rcx
  _OWORD *ActivityIdThread; // rax
  int v8; // ebx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  void *ThreadHandle; // [rsp+80h] [rbp+8h] BYREF

  ThreadHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  if ( a2 )
  {
    v4 = StartContext + 88;
    ActivityIdIrp = IoGetActivityIdIrp(a2, StartContext + 88);
    v6 = 0;
    if ( ActivityIdIrp >= 0 )
      v6 = v4;
  }
  else
  {
    ActivityIdThread = (_OWORD *)IoGetActivityIdThread();
    if ( ActivityIdThread )
    {
      v6 = StartContext + 88;
      *(_OWORD *)(StartContext + 88) = *ActivityIdThread;
    }
    else
    {
      v6 = 0;
    }
  }
  *((_QWORD *)StartContext + 10) = v6;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 512;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = PsCreateSystemThread(
         &ThreadHandle,
         0x1FFFFFu,
         &ObjectAttributes,
         0,
         0,
         (PKSTART_ROUTINE)RefsFspDispatch,
         StartContext);
  if ( v8 >= 0 )
    return ZwClose(ThreadHandle);
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(v8);
  return RefsExtendedCompleteRequestInternal(StartContext, a2, (unsigned int)v8);
}

```

## disassembly

```asm
0x1c00aa528  mov     rax, rsp
0x1c00aa52b  mov     [rax+10h], rbx
0x1c00aa52f  mov     [rax+18h], rsi
0x1c00aa533  push    rdi
0x1c00aa534  sub     rsp, 70h
0x1c00aa538  and     qword ptr [rax+8], 0
0x1c00aa53d  mov     rsi, rdx
0x1c00aa540  and     dword ptr [rax-34h], 0
0x1c00aa544  mov     rdi, rcx
0x1c00aa547  and     dword ptr [rax-1Ch], 0
0x1c00aa54b  test    rdx, rdx
0x1c00aa54e  jz      short loc_1C00AA570
0x1c00aa550  lea     rbx, [rcx+58h]
0x1c00aa554  mov     rcx, rsi
0x1c00aa557  mov     rdx, rbx
0x1c00aa55a  call    cs:__imp_IoGetActivityIdIrp
0x1c00aa561  nop     dword ptr [rax+rax+00h]
0x1c00aa566  xor     ecx, ecx
0x1c00aa568  test    eax, eax
0x1c00aa56a  cmovns  rcx, rbx
0x1c00aa56e  jmp     short loc_1C00AA590
0x1c00aa570  call    cs:__imp_IoGetActivityIdThread
0x1c00aa577  nop     dword ptr [rax+rax+00h]
0x1c00aa57c  test    rax, rax
0x1c00aa57f  jz      short loc_1C00AA58E
0x1c00aa581  movups  xmm0, xmmword ptr [rax]
0x1c00aa584  lea     rcx, [rdi+58h]
0x1c00aa588  movdqu  xmmword ptr [rcx], xmm0
0x1c00aa58c  jmp     short loc_1C00AA590
0x1c00aa58e  xor     ecx, ecx
0x1c00aa590  mov     [rdi+50h], rcx
0x1c00aa594  lea     rax, RefsFspDispatch
0x1c00aa59b  and     [rsp+78h+ObjectAttributes.RootDirectory], 0
0x1c00aa5a1  lea     r8, [rsp+78h+ObjectAttributes]; ObjectAttributes
0x1c00aa5a6  and     [rsp+78h+ObjectAttributes.ObjectName], 0
0x1c00aa5ac  lea     rcx, [rsp+78h+ThreadHandle]; ThreadHandle
0x1c00aa5b4  xorps   xmm0, xmm0
0x1c00aa5b7  mov     [rsp+78h+StartContext], rdi; StartContext
0x1c00aa5bc  mov     [rsp+78h+StartRoutine], rax; StartRoutine
0x1c00aa5c1  xor     r9d, r9d; ProcessHandle
0x1c00aa5c4  and     [rsp+78h+var_58], 0
0x1c00aa5ca  mov     edx, 1FFFFFh; DesiredAccess
0x1c00aa5cf  mov     [rsp+78h+ObjectAttributes.Length], 30h ; '0'
0x1c00aa5d7  mov     [rsp+78h+ObjectAttributes.Attributes], 200h
0x1c00aa5df  movdqu  xmmword ptr [rsp+78h+ObjectAttributes.SecurityDescriptor], xmm0
0x1c00aa5e5  call    cs:__imp_PsCreateSystemThread
0x1c00aa5ec  nop     dword ptr [rax+rax+00h]
0x1c00aa5f1  mov     ebx, eax
0x1c00aa5f3  test    eax, eax
0x1c00aa5f5  js      short loc_1C00AA60D
0x1c00aa5f7  mov     rcx, [rsp+78h+ThreadHandle]; Handle
0x1c00aa5ff  call    cs:__imp_ZwClose
0x1c00aa606  nop     dword ptr [rax+rax+00h]
0x1c00aa60b  jmp     short loc_1C00AA639
0x1c00aa60d  mov     al, cs:RefsStatusDebugEnabled
0x1c00aa613  test    al, al
0x1c00aa615  jz      short loc_1C00AA62B
0x1c00aa617  mov     r8d, 476h
0x1c00aa61d  lea     rdx, aWorkqueC; "workque.c"
0x1c00aa624  mov     ecx, ebx; Status
0x1c00aa626  call    RefsStatusDebug
0x1c00aa62b  mov     r8d, ebx
0x1c00aa62e  mov     rdx, rsi
0x1c00aa631  mov     rcx, rdi
0x1c00aa634  call    RefsExtendedCompleteRequestInternal
0x1c00aa639  lea     r11, [rsp+78h+var_8]
0x1c00aa63e  mov     rbx, [r11+18h]
0x1c00aa642  mov     rsi, [r11+20h]
0x1c00aa646  mov     rsp, r11
0x1c00aa649  pop     rdi
0x1c00aa64a  retn
```
