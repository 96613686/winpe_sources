# DllGetVersion

- ea: `0x1800156e0`
- end: `0x180015777`
- name: `DllGetVersion`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180013624`
- `0x180014dc0`
- `0x18001562a`
- `0x1800156e0`

## pseudocode

```c
__int64 __fastcall DllGetVersion(_DWORD *a1)
{
  __int64 result; // rax
  signed __int32 v3[8]; // [rsp+0h] [rbp-128h] BYREF
  _BYTE v4[6]; // [rsp+20h] [rbp-108h] BYREF
  __int16 v5; // [rsp+26h] [rbp-102h]

  if ( *a1 >= 0x14u )
  {
    if ( !byte_180021110 )
    {
      memset_0(v4, 0, 0xE8u);
      RtlGetVersionResource(&_ImageBase, 0, 2, v4);
      word_180021114 = v5;
      _InterlockedOr(v3, 0);
      byte_180021110 = 1;
    }
    result = (unsigned __int16)word_180021114;
    a1[4] = (unsigned __int16)word_180021114;
    a1[3] = 327680;
  }
  return result;
}

```

## disassembly

```asm
0x1800156e0  push    rbx
0x1800156e2  sub     rsp, 120h
0x1800156e9  mov     rax, cs:__security_cookie
0x1800156f0  xor     rax, rsp
0x1800156f3  mov     [rsp+128h+var_18], rax
0x1800156fb  cmp     dword ptr [rcx], 14h
0x1800156fe  mov     rbx, rcx
0x180015701  jb      short loc_18001575E
0x180015703  cmp     cs:byte_180021110, 0
0x18001570a  jnz     short loc_18001574D
0x18001570c  xor     edx, edx; Val
0x18001570e  lea     rcx, [rsp+128h+var_108]; void *
0x180015713  mov     r8d, 0E8h; Size
0x180015719  call    memset_0
0x18001571e  xor     edx, edx
0x180015720  lea     r9, [rsp+128h+var_108]
0x180015725  lea     rcx, __ImageBase
0x18001572c  lea     r8d, [rdx+2]
0x180015730  call    RtlGetVersionResource
0x180015735  movzx   eax, [rsp+128h+var_102]
0x18001573a  mov     cs:word_180021114, ax
0x180015741  lock or [rsp+128h+var_128], 0
0x180015746  mov     cs:byte_180021110, 1
0x18001574d  movzx   eax, cs:word_180021114
0x180015754  mov     [rbx+10h], eax
0x180015757  mov     dword ptr [rbx+0Ch], 50000h
0x18001575e  mov     rcx, [rsp+128h+var_18]
0x180015766  xor     rcx, rsp; StackCookie
0x180015769  call    __security_check_cookie
0x18001576e  add     rsp, 120h
0x180015775  pop     rbx
0x180015776  retn
```
