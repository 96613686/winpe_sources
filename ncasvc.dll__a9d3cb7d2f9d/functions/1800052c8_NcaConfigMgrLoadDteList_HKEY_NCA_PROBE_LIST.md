# NcaConfigMgrLoadDteList(HKEY__ *,NCA_PROBE_LIST_ *)

- ea: `0x1800052c8`
- end: `0x18000538f`
- name: `?NcaConfigMgrLoadDteList@@YAJPEAUHKEY__@@PEAUNCA_PROBE_LIST_@@@Z`
- size: `199`
- prototype: `__int64 __fastcall(HKEY, struct NCA_PROBE_LIST_ *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005770`

## callees

- `0x180004f34`
- `0x1800052c8`
- `0x18001ac78`

## pseudocode

```c
__int64 __fastcall NcaConfigMgrLoadDteList(HKEY a1, struct NCA_PROBE_LIST_ *a2)
{
  int v3; // edi
  unsigned int v4; // ecx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rcx
  DWORD v10; // [rsp+28h] [rbp-20h]

  v3 = NcaArrayCreateFromRegistry(
         (int)a1,
         (int)L"DTEs",
         24,
         (int)NcaProbeConstruct,
         (__int64)NcaProbeEmpty,
         v10,
         (__int64)a2);
  if ( v3 >= 0 )
  {
    v4 = *(_DWORD *)a2;
    v5 = 0;
    if ( *(_DWORD *)a2 )
    {
      v6 = 0;
      do
      {
        v7 = *((_QWORD *)a2 + 1);
        if ( *(_DWORD *)(v7 + 24 * v6) == 2 )
        {
          if ( (_DWORD)v6 != (_DWORD)v5 )
          {
            v8 = 3 * v5;
            *(_OWORD *)(v7 + 8 * v8) = *(_OWORD *)(v7 + 24 * v6);
            *(_QWORD *)(v7 + 8 * v8 + 16) = *(_QWORD *)(v7 + 24 * v6 + 16);
            v4 = *(_DWORD *)a2;
          }
          v5 = (unsigned int)(v5 + 1);
        }
        v6 = (unsigned int)(v6 + 1);
      }
      while ( (unsigned int)v6 < v4 );
    }
    *(_DWORD *)a2 = v5;
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids, (unsigned int)v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800052c8  mov     [rsp+arg_0], rbx
0x1800052cd  push    rdi
0x1800052ce  sub     rsp, 40h
0x1800052d2  mov     [rsp+48h+var_18], rdx; __int64
0x1800052d7  lea     rax, NcaProbeEmpty
0x1800052de  mov     rbx, rdx
0x1800052e1  mov     [rsp+48h+var_28], rax; __int64
0x1800052e6  lea     rdx, aDtes; "DTEs"
0x1800052ed  mov     r8d, 18h; int
0x1800052f3  lea     r9, ?NcaProbeConstruct@@YAJPEAXPEAUHKEY__@@PEBG20PEAH@Z; int
0x1800052fa  call    NcaArrayCreateFromRegistry
0x1800052ff  mov     edi, eax
0x180005301  test    eax, eax
0x180005303  jns     short loc_180005338
0x180005305  mov     rcx, cs:WPP_GLOBAL_Control
0x18000530c  lea     rax, WPP_GLOBAL_Control
0x180005313  cmp     rcx, rax
0x180005316  jz      short loc_180005381
0x180005318  test    byte ptr [rcx+1Ch], 1
0x18000531c  jz      short loc_180005381
0x18000531e  mov     rcx, [rcx+10h]
0x180005322  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x180005329  mov     edx, 21h ; '!'
0x18000532e  mov     r9d, edi
0x180005331  call    WPP_SF_d
0x180005336  jmp     short loc_180005381
0x180005338  mov     ecx, [rbx]
0x18000533a  xor     edx, edx
0x18000533c  test    ecx, ecx
0x18000533e  jz      short loc_18000537F
0x180005340  xor     r8d, r8d
0x180005343  mov     r9, [rbx+8]
0x180005347  lea     r10, [r8+r8*2]
0x18000534b  cmp     dword ptr [r9+r10*8], 2
0x180005350  jnz     short loc_180005377
0x180005352  cmp     r8d, edx
0x180005355  jz      short loc_180005375
0x180005357  movups  xmm0, xmmword ptr [r9+r10*8]
0x18000535c  lea     rcx, [rdx+rdx*2]
0x180005360  movups  xmmword ptr [r9+rcx*8], xmm0
0x180005365  movsd   xmm1, qword ptr [r9+r10*8+10h]
0x18000536c  movsd   qword ptr [r9+rcx*8+10h], xmm1
0x180005373  mov     ecx, [rbx]
0x180005375  inc     edx
0x180005377  inc     r8d
0x18000537a  cmp     r8d, ecx
0x18000537d  jb      short loc_180005343
0x18000537f  mov     [rbx], edx
0x180005381  mov     rbx, [rsp+48h+arg_0]
0x180005386  mov     eax, edi
0x180005388  add     rsp, 40h
0x18000538c  pop     rdi
0x18000538d  retn
```
