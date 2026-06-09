# PcpAllocateAndInitializeSid

- ea: `0x14001df3c`
- end: `0x14001e005`
- name: `PcpAllocateAndInitializeSid`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14001e00c`

## callees

- `0x14000f48c`
- `0x14001df3c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001df63`
- `ntoskrnl!ExAllocatePool2` at `0x14001df63`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14001df4a`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14001df4a`

## pseudocode

```c
__int64 __fastcall PcpAllocateAndInitializeSid(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 *a11)
{
  ULONG v12; // eax
  __int64 Pool2; // rax
  _DWORD *v14; // rdx
  __int64 result; // rax

  v12 = RtlLengthRequiredSid(6u);
  Pool2 = ExAllocatePool2(64, v12, 1701274448);
  v14 = (_DWORD *)Pool2;
  if ( Pool2 )
  {
    *(_WORD *)Pool2 = 1537;
    *(_DWORD *)(Pool2 + 2) = *(_DWORD *)a1;
    *(_WORD *)(Pool2 + 6) = *(_WORD *)(a1 + 4);
    *(_DWORD *)(Pool2 + 28) = -249309484;
    *(_DWORD *)(Pool2 + 24) = -341646398;
    *(_DWORD *)(Pool2 + 20) = 861291880;
    *a11 = Pool2;
    result = 0;
    v14[4] = -1146866740;
    v14[3] = 1659118645;
    v14[2] = 80;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_0a0383b750aa364b280d5887b3b80ddf_Traceguids);
    }
    return 3221225626LL;
  }
  return result;
}

```

## disassembly

```asm
0x14001df3c  push    rbx
0x14001df3e  sub     rsp, 20h
0x14001df42  mov     rbx, rcx
0x14001df45  mov     ecx, 6; SubAuthorityCount
0x14001df4a  call    cs:__imp_RtlLengthRequiredSid
0x14001df51  nop     dword ptr [rax+rax+00h]
0x14001df56  mov     edx, eax
0x14001df58  mov     ecx, 40h ; '@'
0x14001df5d  mov     r8d, 65676350h
0x14001df63  call    cs:__imp_ExAllocatePool2
0x14001df6a  nop     dword ptr [rax+rax+00h]
0x14001df6f  mov     rdx, rax
0x14001df72  test    rax, rax
0x14001df75  jnz     short loc_14001DFB5
0x14001df77  mov     rcx, cs:WPP_GLOBAL_Control
0x14001df7e  lea     rax, WPP_GLOBAL_Control
0x14001df85  cmp     rcx, rax
0x14001df88  jz      short loc_14001DFAE
0x14001df8a  cmp     byte ptr [rcx+29h], 2
0x14001df8e  jb      short loc_14001DFAE
0x14001df90  test    dword ptr [rcx+2Ch], 800h
0x14001df97  jz      short loc_14001DFAE
0x14001df99  mov     rcx, [rcx+18h]
0x14001df9d  lea     r8, WPP_0a0383b750aa364b280d5887b3b80ddf_Traceguids
0x14001dfa4  mov     edx, 0Ah
0x14001dfa9  call    WPP_SF_
0x14001dfae  mov     eax, 0C000009Ah
0x14001dfb3  jmp     short loc_14001DFFE
0x14001dfb5  mov     word ptr [rax], 601h
0x14001dfba  mov     eax, [rbx]
0x14001dfbc  mov     [rdx+2], eax
0x14001dfbf  movzx   eax, word ptr [rbx+4]
0x14001dfc3  mov     [rdx+6], ax
0x14001dfc7  mov     rax, [rsp+28h+arg_50]
0x14001dfcf  mov     dword ptr [rdx+1Ch], 0F123D6D4h
0x14001dfd6  mov     dword ptr [rdx+18h], 0EBA2E3C2h
0x14001dfdd  mov     dword ptr [rdx+14h], 33564568h
0x14001dfe4  mov     [rax], rdx
0x14001dfe7  xor     eax, eax
0x14001dfe9  mov     dword ptr [rdx+10h], 0BBA433CCh
0x14001dff0  mov     dword ptr [rdx+0Ch], 62E42435h
0x14001dff7  mov     dword ptr [rdx+8], 50h ; 'P'
0x14001dffe  add     rsp, 20h
0x14001e002  pop     rbx
0x14001e003  retn
```
