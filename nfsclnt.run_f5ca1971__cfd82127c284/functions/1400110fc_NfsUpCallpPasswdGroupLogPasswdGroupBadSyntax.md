# NfsUpCallpPasswdGroupLogPasswdGroupBadSyntax

- ea: `0x1400110fc`
- end: `0x140011198`
- name: `NfsUpCallpPasswdGroupLogPasswdGroupBadSyntax`
- size: `156`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140010da4`
- `0x140011244`

## callees

- `0x1400110fc`
- `0x140018350`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x14001117f`
- `ADVAPI32!EventWrite` at `0x14001117f`
- `ADVAPI32!EventEnabled` at `0x14001115c`
- `ADVAPI32!EventEnabled` at `0x14001115c`

## pseudocode

```c
char __fastcall NfsUpCallpPasswdGroupLogPasswdGroupBadSyntax(__int64 a1, __int64 a2, int a3)
{
  __int64 v3; // rax
  int v4; // eax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-38h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h]
  int v8; // [rsp+38h] [rbp-20h]
  int v9; // [rsp+3Ch] [rbp-1Ch]
  int v10; // [rsp+70h] [rbp+18h] BYREF

  v10 = a3;
  *(_QWORD *)&UserData.Size = 4;
  UserData.Ptr = (ULONGLONG)&v10;
  v3 = -1;
  v7 = a2;
  do
    ++v3;
  while ( *(_WORD *)(a2 + 2 * v3) );
  v4 = 2 * v3 + 2;
  v8 = v4;
  v9 = 0;
  if ( RegHandle )
  {
    LOBYTE(v4) = EventEnabled(RegHandle, &EVENT_NFS_SERVICE_PASSWDGROUP_SYNTAX_ERROR);
    if ( (_BYTE)v4 )
      LOBYTE(v4) = EventWrite(RegHandle, &EVENT_NFS_SERVICE_PASSWDGROUP_SYNTAX_ERROR, 2u, &UserData);
  }
  return v4;
}

```

## disassembly

```asm
0x1400110fc  mov     r11, rsp
0x1400110ff  mov     [r11+18h], r8d
0x140011103  push    rbx
0x140011104  sub     rsp, 50h
0x140011108  mov     rax, cs:__security_cookie
0x14001110f  xor     rax, rsp
0x140011112  mov     [rsp+58h+var_18], rax
0x140011117  lea     rax, [r11+18h]
0x14001111b  mov     qword ptr [r11-30h], 4
0x140011123  xor     ebx, ebx
0x140011125  mov     [r11-38h], rax
0x140011129  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001112d  mov     [r11-28h], rdx
0x140011131  inc     rax
0x140011134  cmp     [rdx+rax*2], bx
0x140011138  jnz     short loc_140011131
0x14001113a  mov     rcx, cs:RegHandle; RegHandle
0x140011141  lea     eax, ds:2[rax*2]
0x140011148  mov     [rsp+58h+var_20], eax
0x14001114c  mov     [rsp+58h+var_1C], ebx
0x140011150  test    rcx, rcx
0x140011153  jz      short loc_140011185
0x140011155  lea     rdx, EVENT_NFS_SERVICE_PASSWDGROUP_SYNTAX_ERROR; EventDescriptor
0x14001115c  call    cs:__imp_EventEnabled
0x140011162  test    al, al
0x140011164  jz      short loc_140011185
0x140011166  mov     rcx, cs:RegHandle; RegHandle
0x14001116d  lea     r9, [rsp+58h+UserData]; UserData
0x140011172  mov     r8d, 2; UserDataCount
0x140011178  lea     rdx, EVENT_NFS_SERVICE_PASSWDGROUP_SYNTAX_ERROR; EventDescriptor
0x14001117f  call    cs:__imp_EventWrite
0x140011185  mov     rcx, [rsp+58h+var_18]
0x14001118a  xor     rcx, rsp; StackCookie
0x14001118d  call    __security_check_cookie
0x140011192  add     rsp, 50h
0x140011196  pop     rbx
0x140011197  retn
```
