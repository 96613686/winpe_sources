# BookKeepingXml::Close(void)

- ea: `0x18000c464`
- end: `0x18000c548`
- name: `?Close@BookKeepingXml@@QEAAJXZ`
- size: `228`
- prototype: `__int64 __fastcall(BookKeepingXml *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000d370`

## callees

- `0x180008630`
- `0x18000c464`
- `0x18000c550`
- `0x18000c68c`
- `0x18000c6e0`

## pseudocode

```c
__int64 __fastcall BookKeepingXml::Close(BookKeepingXml *this)
{
  _QWORD *v2; // rbx
  int v3; // edi
  __int64 v4; // rcx
  __int64 v5; // rdx

  if ( *((_DWORD *)this + 2058) == 50 && *((_DWORD *)this + 2059) == 50 )
  {
    v2 = (_QWORD *)((char *)this + 16);
    if ( *((_QWORD *)this + 2) == -1 )
    {
      v3 = -2147221497;
      goto LABEL_15;
    }
    v3 = BookKeepingXml::CloseNode(this, L"BookKeeping");
    if ( v3 >= 0 )
    {
      v3 = BookKeepingXml::Flush((const WCHAR *)this);
      if ( v3 < 0 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          v5 = 15;
          goto LABEL_9;
        }
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v5 = 14;
LABEL_9:
        WPP_SF_d(*(_QWORD *)(v4 + 16), v5, WPP_9741a39f05e03860cc0b7f50af82ce94_Traceguids, (unsigned int)v3);
      }
    }
  }
  else
  {
    v3 = -2147418113;
    v2 = (_QWORD *)((char *)this + 16);
  }
LABEL_15:
  if ( *v2 != -1 )
    *v2 = -1;
  if ( v3 < 0 )
    BookKeepingXml::Empty(this);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000c464  mov     [rsp+arg_0], rbx
0x18000c469  mov     [rsp+arg_8], rsi
0x18000c46e  push    rdi
0x18000c46f  sub     rsp, 20h
0x18000c473  cmp     dword ptr [rcx+2028h], 32h ; '2'
0x18000c47a  mov     rsi, rcx
0x18000c47d  jnz     loc_18000C514
0x18000c483  cmp     dword ptr [rcx+202Ch], 32h ; '2'
0x18000c48a  jnz     loc_18000C514
0x18000c490  lea     rbx, [rcx+10h]
0x18000c494  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18000c498  jnz     short loc_18000C4A1
0x18000c49a  mov     edi, 80040007h
0x18000c49f  jmp     short loc_18000C51D
0x18000c4a1  mov     rdx, cs:off_18001EEE8; unsigned __int16 *
0x18000c4a8  call    ?CloseNode@BookKeepingXml@@AEAAJPEBG@Z; BookKeepingXml::CloseNode(ushort const *)
0x18000c4ad  mov     edi, eax
0x18000c4af  test    eax, eax
0x18000c4b1  jns     short loc_18000C4E6
0x18000c4b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4ba  lea     rax, WPP_GLOBAL_Control
0x18000c4c1  cmp     rcx, rax
0x18000c4c4  jz      short loc_18000C51D
0x18000c4c6  cmp     byte ptr [rcx+19h], 2
0x18000c4ca  jb      short loc_18000C51D
0x18000c4cc  mov     edx, 0Eh
0x18000c4d1  mov     rcx, [rcx+10h]
0x18000c4d5  lea     r8, WPP_9741a39f05e03860cc0b7f50af82ce94_Traceguids
0x18000c4dc  mov     r9d, edi
0x18000c4df  call    WPP_SF_d
0x18000c4e4  jmp     short loc_18000C51D
0x18000c4e6  mov     rcx, rsi; this
0x18000c4e9  call    ?Flush@BookKeepingXml@@AEAAJXZ; BookKeepingXml::Flush(void)
0x18000c4ee  mov     edi, eax
0x18000c4f0  test    eax, eax
0x18000c4f2  jns     short loc_18000C51D
0x18000c4f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4fb  lea     rax, WPP_GLOBAL_Control
0x18000c502  cmp     rcx, rax
0x18000c505  jz      short loc_18000C51D
0x18000c507  cmp     byte ptr [rcx+19h], 2
0x18000c50b  jb      short loc_18000C51D
0x18000c50d  mov     edx, 0Fh
0x18000c512  jmp     short loc_18000C4D1
0x18000c514  mov     edi, 8000FFFFh
0x18000c519  lea     rbx, [rcx+10h]
0x18000c51d  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18000c521  jz      short loc_18000C52A
0x18000c523  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18000c52a  test    edi, edi
0x18000c52c  jns     short loc_18000C536
0x18000c52e  mov     rcx, rsi; this
0x18000c531  call    ?Empty@BookKeepingXml@@QEAAXXZ; BookKeepingXml::Empty(void)
0x18000c536  mov     rbx, [rsp+28h+arg_0]
0x18000c53b  mov     eax, edi
0x18000c53d  mov     rsi, [rsp+28h+arg_8]
0x18000c542  add     rsp, 20h
0x18000c546  pop     rdi
0x18000c547  retn
```
