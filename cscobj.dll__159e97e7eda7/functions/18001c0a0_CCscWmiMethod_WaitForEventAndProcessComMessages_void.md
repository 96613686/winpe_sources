# CCscWmiMethod::_WaitForEventAndProcessComMessages(void *)

- ea: `0x18001c0a0`
- end: `0x18001c176`
- name: `?_WaitForEventAndProcessComMessages@CCscWmiMethod@@IEAAJPEAX@Z`
- size: `214`
- prototype: `__int64 __fastcall(CCscWmiMethod *__hidden this, void *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019e30`
- `0x18001a490`
- `0x18001ae00`

## callees

- `0x18000f5a4`
- `0x18000f5cc`
- `0x18001c0a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001c107`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001c107`

## pseudocode

```c
__int64 __fastcall CCscWmiMethod::_WaitForEventAndProcessComMessages(CCscWmiMethod *this, void *a2)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  CCscWmiMethod *dwindex; // [rsp+40h] [rbp+8h] BYREF
  HANDLE pHandles; // [rsp+48h] [rbp+10h] BYREF

  pHandles = a2;
  dwindex = this;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 59, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids);
  }
  LODWORD(dwindex) = 0;
  v2 = CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, &pHandles, (LPDWORD)&dwindex);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        61,
        WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
        (unsigned int)v2);
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 60, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids);
  }
  return v3;
}

```

## disassembly

```asm
0x18001c0a0  mov     [rsp+arg_10], rbx
0x18001c0a5  mov     [rsp+pHandles], rdx
0x18001c0aa  mov     [rsp+dwindex], rcx
0x18001c0af  push    rdi
0x18001c0b0  sub     rsp, 30h
0x18001c0b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0bb  lea     rdi, WPP_GLOBAL_Control
0x18001c0c2  cmp     rcx, rdi
0x18001c0c5  jz      short loc_18001C0E5
0x18001c0c7  test    dword ptr [rcx+1Ch], 4000000h
0x18001c0ce  jz      short loc_18001C0E5
0x18001c0d0  mov     rcx, [rcx+10h]
0x18001c0d4  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001c0db  mov     edx, 3Bh ; ';'
0x18001c0e0  call    WPP_SF_
0x18001c0e5  lea     rax, [rsp+38h+dwindex]
0x18001c0ea  mov     dword ptr [rsp+38h+dwindex], 0
0x18001c0f2  lea     r9, [rsp+38h+pHandles]; pHandles
0x18001c0f7  mov     [rsp+38h+lpdwindex], rax; lpdwindex
0x18001c0fc  mov     r8d, 1; cHandles
0x18001c102  or      edx, 0FFFFFFFFh; dwTimeout
0x18001c105  xor     ecx, ecx; dwFlags
0x18001c107  call    cs:__imp_CoWaitForMultipleHandles
0x18001c10d  mov     ebx, eax
0x18001c10f  test    eax, eax
0x18001c111  js      short loc_18001C13F
0x18001c113  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c11a  cmp     rcx, rdi
0x18001c11d  jz      short loc_18001C169
0x18001c11f  test    dword ptr [rcx+1Ch], 4000000h
0x18001c126  jz      short loc_18001C169
0x18001c128  mov     rcx, [rcx+10h]
0x18001c12c  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001c133  mov     edx, 3Ch ; '<'
0x18001c138  call    WPP_SF_
0x18001c13d  jmp     short loc_18001C169
0x18001c13f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c146  cmp     rcx, rdi
0x18001c149  jz      short loc_18001C169
0x18001c14b  test    byte ptr [rcx+1Ch], 2
0x18001c14f  jz      short loc_18001C169
0x18001c151  mov     rcx, [rcx+10h]
0x18001c155  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001c15c  mov     edx, 3Dh ; '='
0x18001c161  mov     r9d, ebx
0x18001c164  call    WPP_SF_d
0x18001c169  mov     eax, ebx
0x18001c16b  mov     rbx, [rsp+38h+arg_10]
0x18001c170  add     rsp, 30h
0x18001c174  pop     rdi
0x18001c175  retn
```
