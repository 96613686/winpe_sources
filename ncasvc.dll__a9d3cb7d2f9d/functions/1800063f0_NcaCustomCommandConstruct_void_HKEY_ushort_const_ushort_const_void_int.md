# NcaCustomCommandConstruct(void *,HKEY__ *,ushort const *,ushort const *,void *,int *)

- ea: `0x1800063f0`
- end: `0x18000645f`
- name: `?NcaCustomCommandConstruct@@YAJPEAXPEAUHKEY__@@PEBG20PEAH@Z`
- size: `111`
- prototype: `__int64 __fastcall(void *, HKEY, const unsigned __int16 *, unsigned __int16 *, void *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180004f34`
- `0x1800063f0`
- `0x180006d70`
- `0x180019c70`

## pseudocode

```c
__int64 __fastcall NcaCustomCommandConstruct(
        void *a1,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        void *a5,
        int *a6)
{
  __int64 v6; // rdx
  int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // r9

  v7 = NcaStringCopy(a4);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids,
        (unsigned int)v7);
    goto LABEL_6;
  }
  *a6 = 1;
  if ( !*a6 )
LABEL_6:
    NcaCustomCommandEmpty(a5, v6, v8, v9);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800063f0  push    rbx
0x1800063f2  sub     rsp, 20h
0x1800063f6  mov     rdx, [rsp+28h+arg_20]
0x1800063fb  mov     rcx, r9; Src
0x1800063fe  call    NcaStringCopy
0x180006403  mov     ebx, eax
0x180006405  test    eax, eax
0x180006407  jns     short loc_18000643C
0x180006409  mov     rcx, cs:WPP_GLOBAL_Control
0x180006410  lea     rax, WPP_GLOBAL_Control
0x180006417  cmp     rcx, rax
0x18000641a  jz      short loc_18000644C
0x18000641c  test    byte ptr [rcx+1Ch], 1
0x180006420  jz      short loc_18000644C
0x180006422  mov     rcx, [rcx+10h]
0x180006426  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x18000642d  mov     edx, 1Fh
0x180006432  mov     r9d, ebx
0x180006435  call    WPP_SF_d
0x18000643a  jmp     short loc_18000644C
0x18000643c  mov     rax, [rsp+28h+arg_28]
0x180006441  mov     dword ptr [rax], 1
0x180006447  cmp     dword ptr [rax], 0
0x18000644a  jnz     short loc_180006456
0x18000644c  mov     rcx, [rsp+28h+arg_20]
0x180006451  call    NcaCustomCommandEmpty
0x180006456  mov     eax, ebx
0x180006458  add     rsp, 20h
0x18000645c  pop     rbx
0x18000645d  retn
```
