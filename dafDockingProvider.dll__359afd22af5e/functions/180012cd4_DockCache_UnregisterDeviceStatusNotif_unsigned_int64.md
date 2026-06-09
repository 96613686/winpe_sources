# DockCache::UnregisterDeviceStatusNotif(unsigned __int64)

- ea: `0x180012cd4`
- end: `0x180012dd6`
- name: `?UnregisterDeviceStatusNotif@DockCache@@QEAAJ_K@Z`
- size: `258`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180008738`

## callees

- `0x1800014d0`
- `0x18000c308`
- `0x18001127c`
- `0x180012cd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012cf3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012cf3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012d09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012d90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012d9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012db1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012d09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012d90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012d9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012db1`

## pseudocode

```c
__int64 __fastcall DockCache::UnregisterDeviceStatusNotif(LPCRITICAL_SECTION lpCriticalSection, void *a2)
{
  void **SpinCount; // rax
  void **i; // rdi

  EnterCriticalSection(lpCriticalSection);
  SpinCount = (void **)lpCriticalSection[1].SpinCount;
  for ( i = (void **)*SpinCount; ; i = (void **)*i )
  {
    if ( i == SpinCount )
    {
      LeaveCriticalSection(lpCriticalSection);
      return 2147943568LL;
    }
    if ( i[77] == a2 )
      break;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      69,
      &WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
      lpCriticalSection);
  }
  if ( i != (void **)lpCriticalSection[1].SpinCount )
  {
    *(_QWORD *)i[1] = *i;
    *((_QWORD *)*i + 1) = i[1];
    DeviceStatusNotif::~DeviceStatusNotif((DeviceStatusNotif *)(i + 2));
    operator delete(i);
    --lpCriticalSection[2].DebugInfo;
  }
  LeaveCriticalSection(lpCriticalSection);
  return 0;
}

```

## disassembly

```asm
0x180012cd4  mov     [rsp+arg_8], rbx
0x180012cd9  mov     [rsp+arg_18], rsi
0x180012cde  mov     [rsp+arg_0], rcx
0x180012ce3  push    rdi
0x180012ce4  sub     rsp, 20h
0x180012ce8  mov     rsi, rdx
0x180012ceb  mov     rbx, rcx
0x180012cee  mov     [rsp+28h+lpCriticalSection], rcx
0x180012cf3  call    cs:__imp_EnterCriticalSection
0x180012cf9  nop
0x180012cfa  mov     rax, [rbx+48h]
0x180012cfe  mov     rdi, [rax]
0x180012d01  cmp     rdi, rax
0x180012d04  jnz     short loc_180012D19
0x180012d06  mov     rcx, rbx; lpCriticalSection
0x180012d09  call    cs:__imp_LeaveCriticalSection
0x180012d0f  mov     eax, 80070490h
0x180012d14  jmp     loc_180012DBC
0x180012d19  cmp     [rdi+268h], rsi
0x180012d20  jnz     loc_180012DCC
0x180012d26  lea     rax, WPP_GLOBAL_Control
0x180012d2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d34  cmp     rcx, rax
0x180012d37  jz      short loc_180012D5D
0x180012d39  cmp     byte ptr [rcx+19h], 3
0x180012d3d  jb      short loc_180012D5D
0x180012d3f  test    byte ptr [rcx+1Ch], 1
0x180012d43  jz      short loc_180012D5D
0x180012d45  mov     edx, 45h ; 'E'
0x180012d4a  mov     r9, rbx
0x180012d4d  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x180012d54  mov     rcx, [rcx+10h]
0x180012d58  call    WPP_SF_q
0x180012d5d  cmp     rdi, [rbx+48h]
0x180012d61  jz      short loc_180012D8D
0x180012d63  mov     rcx, [rdi+8]
0x180012d67  mov     rax, [rdi]
0x180012d6a  mov     [rcx], rax
0x180012d6d  mov     rcx, [rdi]
0x180012d70  mov     rax, [rdi+8]
0x180012d74  mov     [rcx+8], rax
0x180012d78  lea     rcx, [rdi+10h]; this
0x180012d7c  call    ??1DeviceStatusNotif@@QEAA@XZ; DeviceStatusNotif::~DeviceStatusNotif(void)
0x180012d81  mov     rcx, rdi; Block
0x180012d84  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012d89  dec     qword ptr [rbx+50h]
0x180012d8d  mov     rcx, rbx; lpCriticalSection
0x180012d90  call    cs:__imp_LeaveCriticalSection
0x180012d96  xor     eax, eax
0x180012d98  jmp     short loc_180012DBC
0x180012d9a  mov     rcx, [rsp+28h+lpCriticalSection]; lpCriticalSection
0x180012d9f  call    cs:__imp_LeaveCriticalSection
0x180012da5  mov     eax, 80004005h
0x180012daa  jmp     short loc_180012DBC
0x180012dac  mov     rcx, [rsp+28h+lpCriticalSection]; lpCriticalSection
0x180012db1  call    cs:__imp_LeaveCriticalSection
0x180012db7  mov     eax, 8007000Eh
0x180012dbc  mov     rbx, [rsp+28h+arg_8]
0x180012dc1  mov     rsi, [rsp+28h+arg_18]
0x180012dc6  add     rsp, 20h
0x180012dca  pop     rdi
0x180012dcb  retn
0x180012dcc  mov     rdi, [rdi]
0x180012dcf  jmp     loc_180012D01
```
