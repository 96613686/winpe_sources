# NcaConfigMgrGetCustomCommandCopy

- ea: `0x1800066ac`
- end: `0x180006736`
- name: `NcaConfigMgrGetCustomCommandCopy`
- size: `138`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a398`

## callees

- `0x180004f34`
- `0x1800066ac`
- `0x180019784`
- `0x180019c70`

## pseudocode

```c
__int64 __fastcall NcaConfigMgrGetCustomCommandCopy(unsigned int a1)
{
  unsigned int v1; // ebx
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  unsigned int v4; // eax

  if ( a1 < (unsigned int)xmmword_180028BE8 )
  {
    v4 = NcaStringCopy(*(void **)(*((_QWORD *)&xmmword_180028BE8 + 1) + 8LL * a1));
    v1 = NcaHResultToWindowsError(v4);
    if ( v1 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v3 = 63;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v1 = 87;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v3 = 62;
LABEL_9:
      WPP_SF_d(v2[2], v3, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids, v1);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800066ac  push    rbx
0x1800066ae  sub     rsp, 20h
0x1800066b2  cmp     ecx, dword ptr cs:xmmword_180028BE8
0x1800066b8  jb      short loc_1800066DD
0x1800066ba  mov     ebx, 57h ; 'W'
0x1800066bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066c6  lea     rax, WPP_GLOBAL_Control
0x1800066cd  cmp     rcx, rax
0x1800066d0  jz      short loc_18000672D
0x1800066d2  test    byte ptr [rcx+1Ch], 1
0x1800066d6  jz      short loc_18000672D
0x1800066d8  lea     edx, [rbx-19h]
0x1800066db  jmp     short loc_18000671A
0x1800066dd  mov     eax, ecx
0x1800066df  mov     rcx, qword ptr cs:xmmword_180028BE8+8
0x1800066e6  mov     rcx, [rcx+rax*8]; Src
0x1800066ea  call    NcaStringCopy
0x1800066ef  mov     ecx, eax
0x1800066f1  call    NcaHResultToWindowsError
0x1800066f6  mov     ebx, eax
0x1800066f8  test    eax, eax
0x1800066fa  jz      short loc_18000672D
0x1800066fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180006703  lea     rax, WPP_GLOBAL_Control
0x18000670a  cmp     rcx, rax
0x18000670d  jz      short loc_18000672D
0x18000670f  test    byte ptr [rcx+1Ch], 1
0x180006713  jz      short loc_18000672D
0x180006715  mov     edx, 3Fh ; '?'
0x18000671a  mov     rcx, [rcx+10h]
0x18000671e  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x180006725  mov     r9d, ebx
0x180006728  call    WPP_SF_d
0x18000672d  mov     eax, ebx
0x18000672f  add     rsp, 20h
0x180006733  pop     rbx
0x180006734  retn
```
