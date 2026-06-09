# DepFSFindOurVolumeContext

- ea: `0x18000844c`
- end: `0x1800084ec`
- name: `DepFSFindOurVolumeContext`
- size: `160`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180008a60`
- `0x180008c10`
- `0x180008d60`

## callees

- `0x180001064`
- `0x18000844c`
- `0x18000f970`

## pseudocode

```c
__int64 __fastcall DepFSFindOurVolumeContext(__int64 a1, __int64 **a2)
{
  __int64 *v2; // rax
  unsigned int v4; // edi
  __int64 *v5; // rbx

  v2 = (__int64 *)qword_1800051A0;
  v4 = -1073741823;
  while ( v2 != &qword_1800051A0 )
  {
    v5 = v2 - 5;
    if ( v2[4] == a1 )
    {
      v4 = ReferenceVolumeContext(v2 - 5, 0);
      if ( (v4 & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_Dq(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_a4016d7e857d3af68560d770380f4c36_Traceguids, v4, v5);
        }
      }
      else
      {
        *a2 = v5;
      }
      return v4;
    }
    v2 = (__int64 *)*v2;
  }
  return v4;
}

```

## disassembly

```asm
0x18000844c  mov     [rsp+arg_0], rbx
0x180008451  mov     [rsp+arg_8], rsi
0x180008456  push    rdi
0x180008457  sub     rsp, 30h
0x18000845b  mov     rax, cs:qword_1800051A0
0x180008462  mov     rsi, rdx
0x180008465  lea     rdx, qword_1800051A0
0x18000846c  mov     edi, 0C0000001h
0x180008471  jmp     short loc_180008480
0x180008473  lea     rbx, [rax-28h]
0x180008477  cmp     [rbx+48h], rcx
0x18000847b  jz      short loc_180008487
0x18000847d  mov     rax, [rax]
0x180008480  cmp     rax, rdx
0x180008483  jnz     short loc_180008473
0x180008485  jmp     short loc_1800084D9
0x180008487  xor     edx, edx
0x180008489  mov     rcx, rbx; Context
0x18000848c  call    ReferenceVolumeContext
0x180008491  mov     edi, eax
0x180008493  test    eax, eax
0x180008495  js      short loc_18000849C
0x180008497  mov     [rsi], rbx
0x18000849a  jmp     short loc_1800084D9
0x18000849c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084a3  lea     rax, WPP_GLOBAL_Control
0x1800084aa  cmp     rcx, rax
0x1800084ad  jz      short loc_1800084D9
0x1800084af  mov     eax, [rcx+2Ch]
0x1800084b2  test    al, 1
0x1800084b4  jz      short loc_1800084D9
0x1800084b6  cmp     byte ptr [rcx+29h], 2
0x1800084ba  jb      short loc_1800084D9
0x1800084bc  mov     rcx, [rcx+18h]
0x1800084c0  lea     r8, WPP_a4016d7e857d3af68560d770380f4c36_Traceguids
0x1800084c7  mov     edx, 16h
0x1800084cc  mov     [rsp+38h+var_18], rbx
0x1800084d1  mov     r9d, edi
0x1800084d4  call    WPP_SF_Dq
0x1800084d9  mov     rbx, [rsp+38h+arg_0]
0x1800084de  mov     eax, edi
0x1800084e0  mov     rsi, [rsp+38h+arg_8]
0x1800084e5  add     rsp, 30h
0x1800084e9  pop     rdi
0x1800084ea  retn
```
