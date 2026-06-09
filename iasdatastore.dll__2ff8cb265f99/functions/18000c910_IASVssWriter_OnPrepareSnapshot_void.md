# IASVssWriter::OnPrepareSnapshot(void)

- ea: `0x18000c910`
- end: `0x18000c9ad`
- name: `?OnPrepareSnapshot@IASVssWriter@@UEAA_NXZ`
- size: `157`
- prototype: `bool __fastcall(IASVssWriter *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180007150`
- `0x18000c910`
- `0x18000d990`

## import_xrefs

- `KERNEL32!TryEnterCriticalSection` at `0x18000c98b`
- `KERNEL32!TryEnterCriticalSection` at `0x18000c98b`
- `KERNEL32!SwitchToThread` at `0x18000c982`
- `KERNEL32!SwitchToThread` at `0x18000c982`
- `KERNEL32!EnterCriticalSection` at `0x18000c99a`
- `KERNEL32!EnterCriticalSection` at `0x18000c99a`

## pseudocode

```c
char __fastcall IASVssWriter::OnPrepareSnapshot(IASVssWriter *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  int v3; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("OnPrepareSnapshot Event Raised");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_51d954edd6d93851aca784e64cc7fb39_Traceguids, "NPSDS");
  }
  _InterlockedExchange((volatile __int32 *)this + 16, 1);
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  v3 = 0;
  while ( !TryEnterCriticalSection(v2) )
  {
    if ( ++v3 >= 100 )
    {
      EnterCriticalSection(v2);
      return 1;
    }
    SwitchToThread();
  }
  return 1;
}

```

## disassembly

```asm
0x18000c910  mov     [rsp+arg_0], rbx
0x18000c915  push    rdi
0x18000c916  sub     rsp, 20h
0x18000c91a  mov     rdi, rcx
0x18000c91d  mov     rax, cs:WPP_GLOBAL_Control
0x18000c924  lea     rcx, WPP_GLOBAL_Control
0x18000c92b  cmp     rax, rcx
0x18000c92e  jz      short loc_18000C96B
0x18000c930  cmp     byte ptr [rax+19h], 4
0x18000c934  jb      short loc_18000C96B
0x18000c936  test    byte ptr [rax+1Ch], 10h
0x18000c93a  jz      short loc_18000C96B
0x18000c93c  lea     rcx, aOnpreparesnaps; "OnPrepareSnapshot Event Raised"
0x18000c943  call    WppDbgPrint
0x18000c948  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c94f  lea     r9, aNpsds; "NPSDS"
0x18000c956  mov     edx, 0Fh
0x18000c95b  lea     r8, WPP_51d954edd6d93851aca784e64cc7fb39_Traceguids
0x18000c962  mov     rcx, [rcx+10h]
0x18000c966  call    WPP_SF_s
0x18000c96b  mov     eax, 1
0x18000c970  xchg    eax, [rdi+40h]
0x18000c973  add     rdi, 18h
0x18000c977  xor     ebx, ebx
0x18000c979  jmp     short loc_18000C988
0x18000c97b  inc     ebx
0x18000c97d  cmp     ebx, 64h ; 'd'
0x18000c980  jge     short loc_18000C997
0x18000c982  call    cs:__imp_SwitchToThread
0x18000c988  mov     rcx, rdi; lpCriticalSection
0x18000c98b  call    cs:__imp_TryEnterCriticalSection
0x18000c991  test    eax, eax
0x18000c993  jz      short loc_18000C97B
0x18000c995  jmp     short loc_18000C9A0
0x18000c997  mov     rcx, rdi; lpCriticalSection
0x18000c99a  call    cs:__imp_EnterCriticalSection
0x18000c9a0  mov     rbx, [rsp+28h+arg_0]
0x18000c9a5  mov     al, 1
0x18000c9a7  add     rsp, 20h
0x18000c9ab  pop     rdi
0x18000c9ac  retn
```
