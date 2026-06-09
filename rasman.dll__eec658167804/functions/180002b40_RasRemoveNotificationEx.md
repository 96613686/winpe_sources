# RasRemoveNotificationEx

- ea: `0x180002b40`
- end: `0x180002c0b`
- name: `RasRemoveNotificationEx`
- size: `203`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002b40`
- `0x180002f80`
- `0x180021000`

## pseudocode

```c
__int64 __fastcall RasRemoveNotificationEx(unsigned int a1)
{
  __int64 result; // rax
  unsigned int v3; // ebx
  PVOID *v4; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 694, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  result = SubmitLocalRequest(0x8Cu, a1);
  v3 = result;
  if ( !(_DWORD)result )
    goto LABEL_4;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return result;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      695,
      &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
      (unsigned int)result);
LABEL_4:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 696, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180002b40  mov     [rsp+arg_0], rbx
0x180002b45  push    rdi
0x180002b46  sub     rsp, 20h
0x180002b4a  mov     ebx, ecx
0x180002b4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b53  lea     rdi, WPP_GLOBAL_Control
0x180002b5a  cmp     rcx, rdi
0x180002b5d  jz      short loc_180002B65
0x180002b5f  test    byte ptr [rcx+1Ch], 40h
0x180002b63  jnz     short loc_180002BB6
0x180002b65  mov     ecx, 8Ch
0x180002b6a  mov     edx, ebx
0x180002b6c  call    SubmitLocalRequest
0x180002b71  mov     ebx, eax
0x180002b73  test    eax, eax
0x180002b75  jnz     short loc_180002BD6
0x180002b77  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b7e  cmp     rcx, rdi
0x180002b81  jnz     short loc_180002B90
0x180002b83  mov     eax, ebx
0x180002b85  mov     rbx, [rsp+28h+arg_0]
0x180002b8a  add     rsp, 20h
0x180002b8e  pop     rdi
0x180002b8f  retn
0x180002b90  test    byte ptr [rcx+1Ch], 40h
0x180002b94  jz      short loc_180002B83
0x180002b96  cmp     byte ptr [rcx+19h], 6
0x180002b9a  jb      short loc_180002B83
0x180002b9c  mov     rcx, [rcx+10h]
0x180002ba0  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180002ba7  mov     edx, 2B8h
0x180002bac  mov     r9d, ebx
0x180002baf  call    WPP_SF_d
0x180002bb4  jmp     short loc_180002B83
0x180002bb6  cmp     byte ptr [rcx+19h], 6
0x180002bba  jb      short loc_180002B65
0x180002bbc  mov     rcx, [rcx+10h]
0x180002bc0  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180002bc7  mov     edx, 2B6h
0x180002bcc  mov     r9d, ebx
0x180002bcf  call    WPP_SF_d
0x180002bd4  jmp     short loc_180002B65
0x180002bd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bdd  cmp     rcx, rdi
0x180002be0  jz      short loc_180002B85
0x180002be2  test    byte ptr [rcx+1Ch], 40h
0x180002be6  jz      short loc_180002B7E
0x180002be8  cmp     byte ptr [rcx+19h], 2
0x180002bec  jb      short loc_180002B7E
0x180002bee  mov     rcx, [rcx+10h]
0x180002bf2  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180002bf9  mov     edx, 2B7h
0x180002bfe  mov     r9d, ebx
0x180002c01  call    WPP_SF_d
0x180002c06  jmp     loc_180002B77
```
