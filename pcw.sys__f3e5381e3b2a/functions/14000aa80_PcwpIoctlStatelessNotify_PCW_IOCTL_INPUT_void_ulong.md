# PcwpIoctlStatelessNotify(PCW_IOCTL_INPUT *,void *,ulong *)

- ea: `0x14000aa80`
- end: `0x14000ab40`
- name: `?PcwpIoctlStatelessNotify@@YAJPEATPCW_IOCTL_INPUT@@PEAXPEAK@Z`
- size: `192`
- prototype: `__int64 __fastcall(unsigned __int64, void *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400099e0`
- `0x140009a08`
- `0x14000aa80`
- `0x14000c240`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14000aaae`
- `ntoskrnl!ProbeForRead` at `0x14000aaae`

## pseudocode

```c
__int64 __fastcall PcwpIoctlStatelessNotify(unsigned __int64 a1, void *a2, unsigned int *a3)
{
  unsigned int v6; // eax
  int v7; // edi
  unsigned int v9; // ebx
  struct _UNICODE_STRING v10; // [rsp+40h] [rbp-38h] BYREF

  v10 = 0;
  v6 = *(_DWORD *)(a1 + 16);
  if ( v6 )
    ProbeForRead(*(volatile void **)(a1 + 8), v6, 1u);
  v7 = AllocatedUnicodeString::Capture(
         (AllocatedUnicodeString *)&v10,
         *(const unsigned __int16 **)(a1 + 32),
         *(_WORD *)(a1 + 26),
         UserMode);
  if ( v7 >= 0 )
  {
    v9 = PcwpSendStatelessNotification(
           &v10,
           *(_DWORD *)(a1 + 20),
           (union _LARGE_INTEGER *)(a1 & -(__int64)(*(_BYTE *)(a1 + 24) != 0)),
           *(void **)(a1 + 8),
           *(_DWORD *)(a1 + 16),
           a2,
           *a3,
           a3);
    AllocatedUnicodeString::~AllocatedUnicodeString((AllocatedUnicodeString *)&v10);
    return v9;
  }
  else
  {
    AllocatedUnicodeString::~AllocatedUnicodeString((AllocatedUnicodeString *)&v10);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x14000aa80  push    rbx
0x14000aa82  push    rsi
0x14000aa83  push    rdi
0x14000aa84  push    r14
0x14000aa86  sub     rsp, 58h
0x14000aa8a  mov     rsi, r8
0x14000aa8d  mov     r14, rdx
0x14000aa90  mov     rbx, rcx
0x14000aa93  xorps   xmm0, xmm0
0x14000aa96  movups  xmmword ptr [rsp+78h+var_38.Length], xmm0
0x14000aa9b  mov     eax, [rcx+10h]
0x14000aa9e  test    eax, eax
0x14000aaa0  jz      short loc_14000AACC
0x14000aaa2  mov     edx, eax; Length
0x14000aaa4  mov     r8d, 1; Alignment
0x14000aaaa  mov     rcx, [rcx+8]; Address
0x14000aaae  call    cs:__imp_ProbeForRead
0x14000aab5  nop     dword ptr [rax+rax+00h]
0x14000aaba  jmp     short loc_14000AACC
0x14000aabc  mov     ebx, eax
0x14000aabe  lea     rcx, [rsp+78h+var_38]; this
0x14000aac3  call    ??1AllocatedUnicodeString@@QEAA@XZ; AllocatedUnicodeString::~AllocatedUnicodeString(void)
0x14000aac8  mov     eax, ebx
0x14000aaca  jmp     short loc_14000AB35
0x14000aacc  mov     r9d, 1; enum _MODE
0x14000aad2  movzx   r8d, word ptr [rbx+1Ah]; unsigned __int16
0x14000aad7  mov     rdx, [rbx+20h]; unsigned __int16 *
0x14000aadb  lea     rcx, [rsp+78h+var_38]; this
0x14000aae0  call    ?Capture@AllocatedUnicodeString@@QEAAJPEBGGW4_MODE@@@Z; AllocatedUnicodeString::Capture(ushort const *,ushort,_MODE)
0x14000aae5  mov     edi, eax
0x14000aae7  lea     rcx, [rsp+78h+var_38]; struct _UNICODE_STRING *
0x14000aaec  test    eax, eax
0x14000aaee  jns     short loc_14000AAF9
0x14000aaf0  call    ??1AllocatedUnicodeString@@QEAA@XZ; AllocatedUnicodeString::~AllocatedUnicodeString(void)
0x14000aaf5  mov     eax, edi
0x14000aaf7  jmp     short loc_14000AB35
0x14000aaf9  mov     al, [rbx+18h]
0x14000aafc  neg     al
0x14000aafe  sbb     r8, r8
0x14000ab01  and     r8, rbx; union _LARGE_INTEGER *
0x14000ab04  mov     [rsp+78h+var_40], rsi; unsigned int *
0x14000ab09  mov     eax, [rsi]
0x14000ab0b  mov     [rsp+78h+var_48], eax; unsigned int
0x14000ab0f  mov     [rsp+78h+var_50], r14; void *
0x14000ab14  mov     eax, [rbx+10h]
0x14000ab17  mov     [rsp+78h+var_58], eax; unsigned int
0x14000ab1b  mov     r9, [rbx+8]; void *
0x14000ab1f  mov     edx, [rbx+14h]; unsigned int
0x14000ab22  call    ?PcwpSendStatelessNotification@@YAJPEBU_UNICODE_STRING@@KPEAT_LARGE_INTEGER@@PEAXK2KPEAK@Z; PcwpSendStatelessNotification(_UNICODE_STRING const *,ulong,_LARGE_INTEGER *,void *,ulong,void *,ulong,ulong *)
0x14000ab27  mov     ebx, eax
0x14000ab29  lea     rcx, [rsp+78h+var_38]; this
0x14000ab2e  call    ??1AllocatedUnicodeString@@QEAA@XZ; AllocatedUnicodeString::~AllocatedUnicodeString(void)
0x14000ab33  mov     eax, ebx
0x14000ab35  add     rsp, 58h
0x14000ab39  pop     r14
0x14000ab3b  pop     rdi
0x14000ab3c  pop     rsi
0x14000ab3d  pop     rbx
0x14000ab3e  retn
```
