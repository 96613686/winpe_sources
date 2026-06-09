# CFdphostSharedService::AddRef(void)

- ea: `0x180002b70`
- end: `0x180002be5`
- name: `?AddRef@CFdphostSharedService@@UEAAKXZ`
- size: `117`
- prototype: `__int64 __fastcall(CFdphostSharedService *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180002b70`
- `0x180002f84`

## pseudocode

```c
__int64 __fastcall CFdphostSharedService::AddRef(CFdphostSharedService *this)
{
  _QWORD *v2; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 14);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 4u )
      WPP_SF_sq(v2[2], 15);
  }
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 2);
}

```

## disassembly

```asm
0x180002b70  mov     [rsp+arg_0], rbx
0x180002b75  push    rdi
0x180002b76  sub     rsp, 30h
0x180002b7a  mov     rbx, rcx
0x180002b7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b84  lea     rdi, WPP_GLOBAL_Control
0x180002b8b  cmp     rcx, rdi
0x180002b8e  jz      short loc_180002BCE
0x180002b90  cmp     byte ptr [rcx+19h], 4
0x180002b94  jb      short loc_180002BB0
0x180002b96  mov     rcx, [rcx+10h]
0x180002b9a  mov     edx, 0Eh
0x180002b9f  mov     [rsp+38h+var_18], rbx
0x180002ba4  call    WPP_SF_sq
0x180002ba9  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bb0  cmp     rcx, rdi
0x180002bb3  jz      short loc_180002BCE
0x180002bb5  cmp     byte ptr [rcx+19h], 4
0x180002bb9  jb      short loc_180002BCE
0x180002bbb  mov     rcx, [rcx+10h]
0x180002bbf  mov     edx, 0Fh
0x180002bc4  mov     [rsp+38h+var_18], rbx
0x180002bc9  call    WPP_SF_sq
0x180002bce  mov     eax, 1
0x180002bd3  lock xadd [rbx+8], eax
0x180002bd8  mov     rbx, [rsp+38h+arg_0]
0x180002bdd  inc     eax
0x180002bdf  add     rsp, 30h
0x180002be3  pop     rdi
0x180002be4  retn
```
