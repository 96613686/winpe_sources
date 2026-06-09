# RasProtocolEnum

- ea: `0x18001d450`
- end: `0x18001d51d`
- name: `RasProtocolEnum`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800030d0`
- `0x18001d450`
- `0x180021ae4`
- `0x180021b14`

## pseudocode

```c
__int64 __fastcall RasProtocolEnum(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  PVOID *v8; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 245, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  v6 = SubmitLocalRequest(0x18u, a2, a1, a3);
  v7 = v6;
  if ( !v6 )
    goto LABEL_10;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v7;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 246, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v6);
LABEL_10:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d(v8[2], 247, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18001d450  push    rbx
0x18001d452  push    rsi
0x18001d453  push    rdi
0x18001d454  push    r14
0x18001d456  sub     rsp, 28h
0x18001d45a  mov     rbx, r8
0x18001d45d  mov     rdi, rdx
0x18001d460  mov     rsi, rcx
0x18001d463  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d46a  lea     r14, WPP_GLOBAL_Control
0x18001d471  cmp     rcx, r14
0x18001d474  jz      short loc_18001D497
0x18001d476  test    byte ptr [rcx+1Ch], 40h
0x18001d47a  jz      short loc_18001D497
0x18001d47c  cmp     byte ptr [rcx+19h], 6
0x18001d480  jb      short loc_18001D497
0x18001d482  mov     rcx, [rcx+10h]
0x18001d486  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d48d  mov     edx, 0F5h
0x18001d492  call    WPP_SF_
0x18001d497  mov     ecx, 18h
0x18001d49c  mov     r9, rbx
0x18001d49f  mov     r8, rsi
0x18001d4a2  mov     rdx, rdi
0x18001d4a5  call    SubmitLocalRequest
0x18001d4aa  mov     ebx, eax
0x18001d4ac  test    eax, eax
0x18001d4ae  jz      short loc_18001D4E0
0x18001d4b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4b7  cmp     rcx, r14
0x18001d4ba  jz      short loc_18001D510
0x18001d4bc  test    byte ptr [rcx+1Ch], 40h
0x18001d4c0  jz      short loc_18001D4E7
0x18001d4c2  cmp     byte ptr [rcx+19h], 2
0x18001d4c6  jb      short loc_18001D4E7
0x18001d4c8  mov     rcx, [rcx+10h]
0x18001d4cc  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d4d3  mov     edx, 0F6h
0x18001d4d8  mov     r9d, eax
0x18001d4db  call    WPP_SF_d
0x18001d4e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4e7  cmp     rcx, r14
0x18001d4ea  jz      short loc_18001D510
0x18001d4ec  test    byte ptr [rcx+1Ch], 40h
0x18001d4f0  jz      short loc_18001D510
0x18001d4f2  cmp     byte ptr [rcx+19h], 6
0x18001d4f6  jb      short loc_18001D510
0x18001d4f8  mov     rcx, [rcx+10h]
0x18001d4fc  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d503  mov     edx, 0F7h
0x18001d508  mov     r9d, ebx
0x18001d50b  call    WPP_SF_d
0x18001d510  mov     eax, ebx
0x18001d512  add     rsp, 28h
0x18001d516  pop     r14
0x18001d518  pop     rdi
0x18001d519  pop     rsi
0x18001d51a  pop     rbx
0x18001d51b  retn
```
