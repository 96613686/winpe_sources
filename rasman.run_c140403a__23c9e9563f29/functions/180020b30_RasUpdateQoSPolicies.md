# RasUpdateQoSPolicies

- ea: `0x180020b30`
- end: `0x180020bf1`
- name: `RasUpdateQoSPolicies`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180002f80`
- `0x180020b30`
- `0x180020fd8`
- `0x180021000`

## pseudocode

```c
__int64 __fastcall RasUpdateQoSPolicies(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  PVOID *v4; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 730, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  v2 = SubmitLocalRequest(0x98u, a1);
  v3 = v2;
  if ( !v2 )
    goto LABEL_10;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 731, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v2);
LABEL_10:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 732, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180020b30  mov     [rsp+arg_0], rbx
0x180020b35  push    rsi
0x180020b36  sub     rsp, 20h
0x180020b3a  mov     rbx, rcx
0x180020b3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b44  lea     rsi, WPP_GLOBAL_Control
0x180020b4b  cmp     rcx, rsi
0x180020b4e  jz      short loc_180020B71
0x180020b50  test    byte ptr [rcx+1Ch], 40h
0x180020b54  jz      short loc_180020B71
0x180020b56  cmp     byte ptr [rcx+19h], 6
0x180020b5a  jb      short loc_180020B71
0x180020b5c  mov     rcx, [rcx+10h]
0x180020b60  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020b67  mov     edx, 2DAh
0x180020b6c  call    WPP_SF_
0x180020b71  mov     ecx, 98h
0x180020b76  mov     rdx, rbx
0x180020b79  call    SubmitLocalRequest
0x180020b7e  mov     ebx, eax
0x180020b80  test    eax, eax
0x180020b82  jz      short loc_180020BB4
0x180020b84  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b8b  cmp     rcx, rsi
0x180020b8e  jz      short loc_180020BE4
0x180020b90  test    byte ptr [rcx+1Ch], 40h
0x180020b94  jz      short loc_180020BBB
0x180020b96  cmp     byte ptr [rcx+19h], 2
0x180020b9a  jb      short loc_180020BBB
0x180020b9c  mov     rcx, [rcx+10h]
0x180020ba0  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020ba7  mov     edx, 2DBh
0x180020bac  mov     r9d, eax
0x180020baf  call    WPP_SF_d
0x180020bb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180020bbb  cmp     rcx, rsi
0x180020bbe  jz      short loc_180020BE4
0x180020bc0  test    byte ptr [rcx+1Ch], 40h
0x180020bc4  jz      short loc_180020BE4
0x180020bc6  cmp     byte ptr [rcx+19h], 6
0x180020bca  jb      short loc_180020BE4
0x180020bcc  mov     rcx, [rcx+10h]
0x180020bd0  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020bd7  mov     edx, 2DCh
0x180020bdc  mov     r9d, ebx
0x180020bdf  call    WPP_SF_d
0x180020be4  mov     eax, ebx
0x180020be6  mov     rbx, [rsp+28h+arg_0]
0x180020beb  add     rsp, 20h
0x180020bef  pop     rsi
0x180020bf0  retn
```
