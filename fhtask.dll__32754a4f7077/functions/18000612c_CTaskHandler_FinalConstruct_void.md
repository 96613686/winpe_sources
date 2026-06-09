# CTaskHandler::FinalConstruct(void)

- ea: `0x18000612c`
- end: `0x1800061e4`
- name: `?FinalConstruct@CTaskHandler@@QEAAJXZ`
- size: `184`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180003358`
- `0x180003600`

## callees

- `0x18000612c`
- `0x1800067a0`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180006148`
- `KERNEL32!InitializeCriticalSection` at `0x180006148`
- `fhsvcctl!FhServiceOpenPipe` at `0x180006170`
- `fhsvcctl!FhServiceOpenPipe` at `0x180006170`

## pseudocode

```c
__int64 __fastcall CTaskHandler::FinalConstruct(struct _RTL_CRITICAL_SECTION *this)
{
  ULONG_PTR *p_SpinCount; // rdi
  int v3; // eax
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9

  p_SpinCount = &this[1].SpinCount;
  this[1].SpinCount = 0;
  InitializeCriticalSection(this + 2);
  LODWORD(this[3].DebugInfo) = 0;
  *(_QWORD *)&this[3].LockCount = 0;
  this[3].OwningThread = 0;
  v3 = FhServiceOpenPipe(0, p_SpinCount);
  if ( v3 >= 0 )
  {
    if ( !*p_SpinCount )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 11;
        v6 = 2147549183LL;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 10;
      v6 = (unsigned int)v3;
LABEL_9:
      WPP_SF_d(v4[2], v5, WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids, v6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000612c  mov     [rsp+arg_0], rbx
0x180006131  push    rdi
0x180006132  sub     rsp, 20h
0x180006136  lea     rdi, [rcx+48h]
0x18000613a  mov     rbx, rcx
0x18000613d  add     rcx, 50h ; 'P'; lpCriticalSection
0x180006141  mov     qword ptr [rdi], 0
0x180006148  call    cs:__imp_InitializeCriticalSection
0x18000614e  mov     rdx, rdi
0x180006151  mov     dword ptr [rbx+78h], 0
0x180006158  xor     ecx, ecx
0x18000615a  mov     qword ptr [rbx+80h], 0
0x180006165  mov     qword ptr [rbx+88h], 0
0x180006170  call    cs:__imp_FhServiceOpenPipe
0x180006176  test    eax, eax
0x180006178  jns     short loc_18000619D
0x18000617a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006181  lea     rdx, WPP_GLOBAL_Control
0x180006188  cmp     rcx, rdx
0x18000618b  jz      short loc_1800061D7
0x18000618d  test    byte ptr [rcx+1Ch], 1
0x180006191  jz      short loc_1800061D7
0x180006193  mov     edx, 0Ah
0x180006198  mov     r9d, eax
0x18000619b  jmp     short loc_1800061C7
0x18000619d  cmp     qword ptr [rdi], 0
0x1800061a1  jnz     short loc_1800061D7
0x1800061a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061aa  lea     rdx, WPP_GLOBAL_Control
0x1800061b1  cmp     rcx, rdx
0x1800061b4  jz      short loc_1800061D7
0x1800061b6  test    byte ptr [rcx+1Ch], 1
0x1800061ba  jz      short loc_1800061D7
0x1800061bc  mov     edx, 0Bh
0x1800061c1  mov     r9d, 8000FFFFh
0x1800061c7  mov     rcx, [rcx+10h]
0x1800061cb  lea     r8, WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids
0x1800061d2  call    WPP_SF_d
0x1800061d7  mov     rbx, [rsp+28h+arg_0]
0x1800061dc  xor     eax, eax
0x1800061de  add     rsp, 20h
0x1800061e2  pop     rdi
0x1800061e3  retn
```
