# RasProtocolCallback

- ea: `0x18001c7d0`
- end: `0x18001c8dc`
- name: `RasProtocolCallback`
- size: `268`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002f80`
- `0x1800119c4`
- `0x18001c7d0`
- `0x180021000`
- `0x180021488`

## pseudocode

```c
__int64 __fastcall RasProtocolCallback(__int64 a1, __int64 a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  unsigned int v7; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 434, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    v5 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 435;
LABEL_20:
      WPP_SF_d(v4[2], v6, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v5);
      return v5;
    }
    return v5;
  }
  v7 = SubmitLocalRequest(0x45u, a1, a2);
  v5 = v7;
  if ( v7 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v5;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_16;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 436, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    v6 = 437;
    goto LABEL_20;
  }
  return v5;
}

```

## disassembly

```asm
0x18001c7d0  mov     [rsp+arg_0], rbx
0x18001c7d5  mov     [rsp+arg_8], rbp
0x18001c7da  push    rdi
0x18001c7db  sub     rsp, 20h
0x18001c7df  mov     rdi, rdx
0x18001c7e2  mov     rbx, rcx
0x18001c7e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c7ec  lea     rbp, WPP_GLOBAL_Control
0x18001c7f3  cmp     rcx, rbp
0x18001c7f6  jz      short loc_18001C81C
0x18001c7f8  test    byte ptr [rcx+1Ch], 40h
0x18001c7fc  jz      short loc_18001C81C
0x18001c7fe  cmp     byte ptr [rcx+19h], 6
0x18001c802  jb      short loc_18001C81C
0x18001c804  mov     rcx, [rcx+10h]
0x18001c808  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c80f  mov     edx, 1B2h
0x18001c814  mov     r9, rbx
0x18001c817  call    WPP_SF_q
0x18001c81c  mov     rcx, rbx
0x18001c81f  call    ValidatePortHandle
0x18001c824  test    eax, eax
0x18001c826  jnz     short loc_18001C854
0x18001c828  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c82f  mov     ebx, 259h
0x18001c834  cmp     rcx, rbp
0x18001c837  jz      loc_18001C8CA
0x18001c83d  test    byte ptr [rcx+1Ch], 40h
0x18001c841  jz      loc_18001C8CA
0x18001c847  cmp     byte ptr [rcx+19h], 2
0x18001c84b  jb      short loc_18001C8CA
0x18001c84d  mov     edx, 1B3h
0x18001c852  jmp     short loc_18001C8B7
0x18001c854  mov     ecx, 45h ; 'E'
0x18001c859  mov     r8, rdi
0x18001c85c  mov     rdx, rbx
0x18001c85f  call    SubmitLocalRequest
0x18001c864  mov     ebx, eax
0x18001c866  test    eax, eax
0x18001c868  jz      short loc_18001C89A
0x18001c86a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c871  cmp     rcx, rbp
0x18001c874  jz      short loc_18001C8CA
0x18001c876  test    byte ptr [rcx+1Ch], 40h
0x18001c87a  jz      short loc_18001C8A1
0x18001c87c  cmp     byte ptr [rcx+19h], 2
0x18001c880  jb      short loc_18001C8A1
0x18001c882  mov     rcx, [rcx+10h]
0x18001c886  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c88d  mov     edx, 1B4h
0x18001c892  mov     r9d, eax
0x18001c895  call    WPP_SF_d
0x18001c89a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c8a1  cmp     rcx, rbp
0x18001c8a4  jz      short loc_18001C8CA
0x18001c8a6  test    byte ptr [rcx+1Ch], 40h
0x18001c8aa  jz      short loc_18001C8CA
0x18001c8ac  cmp     byte ptr [rcx+19h], 6
0x18001c8b0  jb      short loc_18001C8CA
0x18001c8b2  mov     edx, 1B5h
0x18001c8b7  mov     rcx, [rcx+10h]
0x18001c8bb  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c8c2  mov     r9d, ebx
0x18001c8c5  call    WPP_SF_d
0x18001c8ca  mov     rbp, [rsp+28h+arg_8]
0x18001c8cf  mov     eax, ebx
0x18001c8d1  mov     rbx, [rsp+28h+arg_0]
0x18001c8d6  add     rsp, 20h
0x18001c8da  pop     rdi
0x18001c8db  retn
```
