# RasProtocolStarted

- ea: `0x18001d320`
- end: `0x18001d3e1`
- name: `RasProtocolStarted`
- size: `193`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002f80`
- `0x18001d320`
- `0x180020fd8`
- `0x180021000`

## pseudocode

```c
__int64 __fastcall RasProtocolStarted(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  PVOID *v4; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 539, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  v2 = SubmitLocalRequest(0x5Au, a1);
  v3 = v2;
  if ( !v2 )
    goto LABEL_10;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 540, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v2);
LABEL_10:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 541, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18001d320  mov     [rsp+arg_0], rbx
0x18001d325  push    rsi
0x18001d326  sub     rsp, 20h
0x18001d32a  mov     rbx, rcx
0x18001d32d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d334  lea     rsi, WPP_GLOBAL_Control
0x18001d33b  cmp     rcx, rsi
0x18001d33e  jz      short loc_18001D361
0x18001d340  test    byte ptr [rcx+1Ch], 40h
0x18001d344  jz      short loc_18001D361
0x18001d346  cmp     byte ptr [rcx+19h], 6
0x18001d34a  jb      short loc_18001D361
0x18001d34c  mov     rcx, [rcx+10h]
0x18001d350  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d357  mov     edx, 21Bh
0x18001d35c  call    WPP_SF_
0x18001d361  mov     ecx, 5Ah ; 'Z'
0x18001d366  mov     rdx, rbx
0x18001d369  call    SubmitLocalRequest
0x18001d36e  mov     ebx, eax
0x18001d370  test    eax, eax
0x18001d372  jz      short loc_18001D3A4
0x18001d374  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d37b  cmp     rcx, rsi
0x18001d37e  jz      short loc_18001D3D4
0x18001d380  test    byte ptr [rcx+1Ch], 40h
0x18001d384  jz      short loc_18001D3AB
0x18001d386  cmp     byte ptr [rcx+19h], 2
0x18001d38a  jb      short loc_18001D3AB
0x18001d38c  mov     rcx, [rcx+10h]
0x18001d390  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d397  mov     edx, 21Ch
0x18001d39c  mov     r9d, eax
0x18001d39f  call    WPP_SF_d
0x18001d3a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3ab  cmp     rcx, rsi
0x18001d3ae  jz      short loc_18001D3D4
0x18001d3b0  test    byte ptr [rcx+1Ch], 40h
0x18001d3b4  jz      short loc_18001D3D4
0x18001d3b6  cmp     byte ptr [rcx+19h], 6
0x18001d3ba  jb      short loc_18001D3D4
0x18001d3bc  mov     rcx, [rcx+10h]
0x18001d3c0  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d3c7  mov     edx, 21Dh
0x18001d3cc  mov     r9d, ebx
0x18001d3cf  call    WPP_SF_d
0x18001d3d4  mov     eax, ebx
0x18001d3d6  mov     rbx, [rsp+28h+arg_0]
0x18001d3db  add     rsp, 20h
0x18001d3df  pop     rsi
0x18001d3e0  retn
```
