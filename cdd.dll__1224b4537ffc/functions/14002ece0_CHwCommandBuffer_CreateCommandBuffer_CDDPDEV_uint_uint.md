# CHwCommandBuffer::CreateCommandBuffer(CDDPDEV *,uint,uint)

- ea: `0x14002ece0`
- end: `0x14002ee19`
- name: `?CreateCommandBuffer@CHwCommandBuffer@@QEAAJPEAUCDDPDEV@@II@Z`
- size: `313`
- prototype: `__int64 __fastcall(CHwCommandBuffer *this, struct CDDPDEV *, int, ULONG)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001d980`
- `0x14002d4b4`

## callees

- `0x140011220`
- `0x14002ece0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14002edde`
- `ntoskrnl!KeInitializeEvent` at `0x14002edde`
- `ntoskrnl!ExAllocatePool2` at `0x14002ed8d`
- `ntoskrnl!ExAllocatePool2` at `0x14002ed8d`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002ed3c`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002ed3c`
- `watchdog!WdLogSingleEntry0` at `0x14002ed25`
- `watchdog!WdLogSingleEntry0` at `0x14002eda8`
- `watchdog!WdLogSingleEntry0` at `0x14002ed25`
- `watchdog!WdLogSingleEntry0` at `0x14002eda8`
- `WIN32K!EngAllocMem` at `0x14002ed0d`
- `WIN32K!EngAllocMem` at `0x14002ed0d`

## pseudocode

```c
__int64 __fastcall CHwCommandBuffer::CreateCommandBuffer(CHwCommandBuffer *this, struct CDDPDEV *a2, int a3, ULONG a4)
{
  PVOID v7; // rax
  int v8; // ebx
  _QWORD *v9; // rax
  __int64 result; // rax
  __int64 Pool2; // rax

  if ( !*((_QWORD *)this + 2) )
  {
    v7 = EngAllocMem(1u, a4, 0x64646344u);
    *((_QWORD *)this + 2) = v7;
    if ( !v7 )
    {
      WdLogSingleEntry0(6);
      v8 = 109;
LABEL_4:
      WdLogGlobalForLineNumber = v8;
      v9 = (_QWORD *)WdLogNewEntry5_WdLowResource();
      v9[3] = gCddImageInfo;
      v9[4] = (unsigned int)dword_14003E570;
      v9[5] = 215857758;
      result = 3221225495LL;
      WdLogGlobalForLineNumber = v8;
      return result;
    }
  }
  if ( !*((_QWORD *)this + 267) )
  {
    Pool2 = ExAllocatePool2(64, 56, 1684300612);
    *((_QWORD *)this + 267) = Pool2;
    if ( !Pool2 )
    {
      WdLogSingleEntry0(6);
      v8 = 118;
      goto LABEL_4;
    }
    *(_DWORD *)Pool2 = 1;
    *(_QWORD *)(Pool2 + 8) = 0;
    *(_DWORD *)(Pool2 + 16) = 0;
    KeInitializeEvent((PRKEVENT)(Pool2 + 24), SynchronizationEvent, 0);
  }
  *(_QWORD *)this = a2;
  *((_DWORD *)this + 2) = a3;
  *((_QWORD *)this + 264) = (char *)this + 2104;
  *((_QWORD *)this + 263) = (char *)this + 2104;
  CHwCommandBuffer::ResetCommandBuffer(this);
  return 0;
}

```

## disassembly

```asm
0x14002ece0  mov     [rsp+arg_0], rbx
0x14002ece5  mov     [rsp+arg_8], rsi
0x14002ecea  push    rdi
0x14002eceb  sub     rsp, 20h
0x14002ecef  cmp     qword ptr [rcx+10h], 0
0x14002ecf4  mov     edi, r8d
0x14002ecf7  mov     rsi, rdx
0x14002ecfa  mov     rbx, rcx
0x14002ecfd  jnz     short loc_14002ED75
0x14002ecff  mov     r8d, 64646344h; ulTag
0x14002ed05  mov     edx, r9d; cjMemSize
0x14002ed08  mov     ecx, 1; fl
0x14002ed0d  call    cs:__imp_EngAllocMem
0x14002ed14  nop     dword ptr [rax+rax+00h]
0x14002ed19  mov     [rbx+10h], rax
0x14002ed1d  test    rax, rax
0x14002ed20  jnz     short loc_14002ED75
0x14002ed22  lea     ecx, [rax+6]
0x14002ed25  call    cs:__imp_WdLogSingleEntry0
0x14002ed2c  nop     dword ptr [rax+rax+00h]
0x14002ed31  mov     ebx, 6Dh ; 'm'
0x14002ed36  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002ed3c  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x14002ed43  nop     dword ptr [rax+rax+00h]
0x14002ed48  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002ed4f  mov     [rax+18h], rcx
0x14002ed53  mov     ecx, cs:dword_14003E570
0x14002ed59  mov     [rax+20h], rcx
0x14002ed5d  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002ed65  mov     eax, 0C0000017h
0x14002ed6a  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002ed70  jmp     loc_14002EE08
0x14002ed75  cmp     qword ptr [rbx+858h], 0
0x14002ed7d  jnz     short loc_14002EDEA
0x14002ed7f  mov     edx, 38h ; '8'
0x14002ed84  mov     r8d, 64646344h
0x14002ed8a  lea     ecx, [rdx+8]
0x14002ed8d  call    cs:__imp_ExAllocatePool2
0x14002ed94  nop     dword ptr [rax+rax+00h]
0x14002ed99  mov     [rbx+858h], rax
0x14002eda0  test    rax, rax
0x14002eda3  jnz     short loc_14002EDBE
0x14002eda5  lea     ecx, [rax+6]
0x14002eda8  call    cs:__imp_WdLogSingleEntry0
0x14002edaf  nop     dword ptr [rax+rax+00h]
0x14002edb4  mov     ebx, 76h ; 'v'
0x14002edb9  jmp     loc_14002ED36
0x14002edbe  xor     r8d, r8d; State
0x14002edc1  mov     dword ptr [rax], 1
0x14002edc7  lea     rcx, [rax+18h]; Event
0x14002edcb  mov     qword ptr [rax+8], 0
0x14002edd3  mov     dword ptr [rax+10h], 0
0x14002edda  lea     edx, [r8+1]; Type
0x14002edde  call    cs:__imp_KeInitializeEvent
0x14002ede5  nop     dword ptr [rax+rax+00h]
0x14002edea  lea     rax, [rbx+838h]
0x14002edf1  mov     [rbx], rsi
0x14002edf4  mov     [rbx+8], edi
0x14002edf7  mov     rcx, rbx; this
0x14002edfa  mov     [rax+8], rax
0x14002edfe  mov     [rax], rax
0x14002ee01  call    ?ResetCommandBuffer@CHwCommandBuffer@@QEAAXXZ; CHwCommandBuffer::ResetCommandBuffer(void)
0x14002ee06  xor     eax, eax
0x14002ee08  mov     rbx, [rsp+28h+arg_0]
0x14002ee0d  mov     rsi, [rsp+28h+arg_8]
0x14002ee12  add     rsp, 20h
0x14002ee16  pop     rdi
0x14002ee17  retn
```
