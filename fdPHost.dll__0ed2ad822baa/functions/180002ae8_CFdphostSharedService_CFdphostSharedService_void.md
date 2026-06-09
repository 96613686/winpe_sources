# CFdphostSharedService::~CFdphostSharedService(void)

- ea: `0x180002ae8`
- end: `0x180002b5b`
- name: `??1CFdphostSharedService@@QEAA@XZ`
- size: `115`
- prototype: `void __fastcall(CFdphostSharedService *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180002e50`

## callees

- `0x180002ae8`
- `0x180002f84`

## pseudocode

```c
void __fastcall CFdphostSharedService::~CFdphostSharedService(CFdphostSharedService *this)
{
  _QWORD *v1; // rcx

  *(_QWORD *)this = &CFdphostSharedService::`vftable';
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 12);
      v1 = WPP_GLOBAL_Control;
    }
    if ( v1 != &WPP_GLOBAL_Control && *((_BYTE *)v1 + 25) >= 4u )
      WPP_SF_sq(v1[2], 13);
  }
}

```

## disassembly

```asm
0x180002ae8  mov     [rsp+arg_0], rbx
0x180002aed  push    rdi
0x180002aee  sub     rsp, 30h
0x180002af2  lea     rax, ??_7CFdphostSharedService@@6B@; const CFdphostSharedService::`vftable'
0x180002af9  mov     rbx, rcx
0x180002afc  mov     [rcx], rax
0x180002aff  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b06  lea     rdi, WPP_GLOBAL_Control
0x180002b0d  cmp     rcx, rdi
0x180002b10  jz      short loc_180002B50
0x180002b12  cmp     byte ptr [rcx+19h], 4
0x180002b16  jb      short loc_180002B32
0x180002b18  mov     rcx, [rcx+10h]
0x180002b1c  mov     edx, 0Ch
0x180002b21  mov     [rsp+38h+var_18], rbx
0x180002b26  call    WPP_SF_sq
0x180002b2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b32  cmp     rcx, rdi
0x180002b35  jz      short loc_180002B50
0x180002b37  cmp     byte ptr [rcx+19h], 4
0x180002b3b  jb      short loc_180002B50
0x180002b3d  mov     rcx, [rcx+10h]
0x180002b41  mov     edx, 0Dh
0x180002b46  mov     [rsp+38h+var_18], rbx
0x180002b4b  call    WPP_SF_sq
0x180002b50  mov     rbx, [rsp+38h+arg_0]
0x180002b55  add     rsp, 30h
0x180002b59  pop     rdi
0x180002b5a  retn
```
