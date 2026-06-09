# NcaConfigMgrGetProbeObjectCopy(ulong,NCA_PROBE_LIST_ *,NCA_PROBE_ *)

- ea: `0x1800050d8`
- end: `0x180005177`
- name: `?NcaConfigMgrGetProbeObjectCopy@@YAKKPEAUNCA_PROBE_LIST_@@PEAUNCA_PROBE_@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(unsigned int, struct NCA_PROBE_LIST_ *, struct NCA_PROBE_ *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180002e90`
- `0x180011744`

## callees

- `0x180004f34`
- `0x1800050d8`
- `0x180019784`
- `0x180019c70`

## pseudocode

```c
__int64 __fastcall NcaConfigMgrGetProbeObjectCopy(unsigned int a1, struct NCA_PROBE_LIST_ *a2, struct NCA_PROBE_ *a3)
{
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rcx
  unsigned int v8; // eax

  if ( a1 < *(_DWORD *)a2 )
  {
    v6 = a1;
    v7 = *((_QWORD *)a2 + 1);
    *(_DWORD *)a3 = *(_DWORD *)(v7 + 24 * v6);
    *((_DWORD *)a3 + 4) = *(_DWORD *)(v7 + 24 * v6 + 16);
    v8 = NcaStringCopy(*(void **)(v7 + 24 * v6 + 8));
    v3 = NcaHResultToWindowsError(v8);
    if ( v3 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 61;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v3 = 87;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 60;
LABEL_9:
      WPP_SF_d(v4[2], v5, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids, v3);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800050d8  push    rbx
0x1800050da  sub     rsp, 20h
0x1800050de  mov     r9, r8
0x1800050e1  cmp     ecx, [rdx]
0x1800050e3  jb      short loc_180005108
0x1800050e5  mov     ebx, 57h ; 'W'
0x1800050ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050f1  lea     rax, WPP_GLOBAL_Control
0x1800050f8  cmp     rcx, rax
0x1800050fb  jz      short loc_18000516E
0x1800050fd  test    byte ptr [rcx+1Ch], 1
0x180005101  jz      short loc_18000516E
0x180005103  lea     edx, [rbx-1Bh]
0x180005106  jmp     short loc_18000515B
0x180005108  mov     eax, ecx
0x18000510a  mov     rcx, [rdx+8]
0x18000510e  lea     rdx, [r9+8]
0x180005112  lea     r8, [rax+rax*2]
0x180005116  mov     eax, [rcx+r8*8]
0x18000511a  mov     [r9], eax
0x18000511d  mov     eax, [rcx+r8*8+10h]
0x180005122  mov     [r9+10h], eax
0x180005126  mov     rcx, [rcx+r8*8+8]; Src
0x18000512b  call    NcaStringCopy
0x180005130  mov     ecx, eax
0x180005132  call    NcaHResultToWindowsError
0x180005137  mov     ebx, eax
0x180005139  test    eax, eax
0x18000513b  jz      short loc_18000516E
0x18000513d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005144  lea     rax, WPP_GLOBAL_Control
0x18000514b  cmp     rcx, rax
0x18000514e  jz      short loc_18000516E
0x180005150  test    byte ptr [rcx+1Ch], 1
0x180005154  jz      short loc_18000516E
0x180005156  mov     edx, 3Dh ; '='
0x18000515b  mov     rcx, [rcx+10h]
0x18000515f  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x180005166  mov     r9d, ebx
0x180005169  call    WPP_SF_d
0x18000516e  mov     eax, ebx
0x180005170  add     rsp, 20h
0x180005174  pop     rbx
0x180005175  retn
```
