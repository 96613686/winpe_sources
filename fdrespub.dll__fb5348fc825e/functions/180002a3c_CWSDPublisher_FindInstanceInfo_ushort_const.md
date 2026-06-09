# CWSDPublisher::FindInstanceInfo(ushort const *)

- ea: `0x180002a3c`
- end: `0x180002aca`
- name: `?FindInstanceInfo@CWSDPublisher@@IEAAPEAUINSTANCE_INFO@@PEBG@Z`
- size: `142`
- prototype: `struct INSTANCE_INFO *__fastcall(CWSDPublisher *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ad0`
- `0x180004498`

## callees

- `0x180001f24`
- `0x180002a3c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180002aa1`
- `msvcrt!_wcsicmp` at `0x180002aa1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ab8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ab8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a88`

## pseudocode

```c
struct INSTANCE_INFO *__fastcall CWSDPublisher::FindInstanceInfo(CWSDPublisher *this, const unsigned __int16 *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  char *v5; // rdi
  char *i; // rbx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids);
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v5 = (char *)this + 176;
  for ( i = (char *)*((_QWORD *)this + 22); i != v5; i = *(char **)i )
  {
    if ( !_wcsicmp(a2, *((const wchar_t **)i + 2)) )
      goto LABEL_9;
  }
  i = 0;
LABEL_9:
  LeaveCriticalSection(v4);
  return (struct INSTANCE_INFO *)i;
}

```

## disassembly

```asm
0x180002a3c  push    rbx
0x180002a3e  push    rbp
0x180002a3f  push    rsi
0x180002a40  push    rdi
0x180002a41  sub     rsp, 38h
0x180002a45  mov     rbp, rdx
0x180002a48  mov     rbx, rcx
0x180002a4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a52  lea     rax, WPP_GLOBAL_Control
0x180002a59  cmp     rcx, rax
0x180002a5c  jz      short loc_180002A7E
0x180002a5e  cmp     byte ptr [rcx+19h], 4
0x180002a62  jb      short loc_180002A7E
0x180002a64  mov     rcx, [rcx+10h]
0x180002a68  lea     r8, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids
0x180002a6f  mov     edx, 27h ; '''
0x180002a74  mov     [rsp+58h+var_38], rbx
0x180002a79  call    WPP_SF_sq
0x180002a7e  lea     rsi, [rbx+88h]
0x180002a85  mov     rcx, rsi; lpCriticalSection
0x180002a88  call    cs:__imp_EnterCriticalSection
0x180002a8e  lea     rdi, [rbx+0B0h]
0x180002a95  mov     rbx, [rdi]
0x180002a98  jmp     short loc_180002AAE
0x180002a9a  mov     rdx, [rbx+10h]; String2
0x180002a9e  mov     rcx, rbp; String1
0x180002aa1  call    cs:__imp__wcsicmp
0x180002aa7  test    eax, eax
0x180002aa9  jz      short loc_180002AB5
0x180002aab  mov     rbx, [rbx]
0x180002aae  cmp     rbx, rdi
0x180002ab1  jnz     short loc_180002A9A
0x180002ab3  xor     ebx, ebx
0x180002ab5  mov     rcx, rsi; lpCriticalSection
0x180002ab8  call    cs:__imp_LeaveCriticalSection
0x180002abe  mov     rax, rbx
0x180002ac1  add     rsp, 38h
0x180002ac5  pop     rdi
0x180002ac6  pop     rsi
0x180002ac7  pop     rbp
0x180002ac8  pop     rbx
0x180002ac9  retn
```
