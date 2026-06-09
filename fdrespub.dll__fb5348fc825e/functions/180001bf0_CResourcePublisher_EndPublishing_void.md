# CResourcePublisher::EndPublishing(void)

- ea: `0x180001bf0`
- end: `0x180001cad`
- name: `?EndPublishing@CResourcePublisher@@UEAAJXZ`
- size: `189`
- prototype: `__int64 __fastcall(CResourcePublisher *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180004a30`
- `0x180004b30`

## callees

- `0x180001bf0`
- `0x180001f24`
- `0x180001f70`
- `0x1800027b0`

## pseudocode

```c
__int64 __fastcall CResourcePublisher::EndPublishing(CResourcePublisher *this)
{
  _BYTE *v2; // rcx
  __int64 v3; // rax
  unsigned int v4; // eax
  unsigned int v5; // ebx
  bool v6; // cf

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_dca0bca380213f5562de9c342e06f597_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = *((_QWORD *)this + 1);
  if ( !v3 || !*(_DWORD *)(v3 + 20) )
  {
    v5 = 1;
    goto LABEL_9;
  }
  v4 = CWSDPublisher::EndPublication(*((CWSDPublisher **)this + 1));
  v2 = WPP_GLOBAL_Control;
  v5 = v4;
  if ( v4 )
  {
LABEL_9:
    v4 = 0;
    v6 = v2[25] < 2u;
    goto LABEL_10;
  }
  v6 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
LABEL_10:
  if ( v2 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v4) = !v6;
    if ( v4 )
      WPP_SF_sqd(*((_QWORD *)v2 + 2), 15, WPP_dca0bca380213f5562de9c342e06f597_Traceguids);
  }
  return v5;
}

```

## disassembly

```asm
0x180001bf0  mov     [rsp+arg_0], rbx
0x180001bf5  mov     [rsp+arg_8], rsi
0x180001bfa  push    rdi
0x180001bfb  sub     rsp, 30h
0x180001bff  mov     rdi, rcx
0x180001c02  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c09  lea     rsi, WPP_GLOBAL_Control
0x180001c10  cmp     rcx, rsi
0x180001c13  jz      short loc_180001C3C
0x180001c15  cmp     byte ptr [rcx+19h], 4
0x180001c19  jb      short loc_180001C3C
0x180001c1b  mov     rcx, [rcx+10h]
0x180001c1f  lea     r8, WPP_dca0bca380213f5562de9c342e06f597_Traceguids
0x180001c26  mov     edx, 0Eh
0x180001c2b  mov     [rsp+38h+var_18], rdi
0x180001c30  call    WPP_SF_sq
0x180001c35  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c3c  mov     rax, [rdi+8]
0x180001c40  test    rax, rax
0x180001c43  jz      short loc_180001C66
0x180001c45  cmp     dword ptr [rax+14h], 0
0x180001c49  jz      short loc_180001C66
0x180001c4b  mov     rcx, rax; this
0x180001c4e  call    ?EndPublication@CWSDPublisher@@QEAAJXZ; CWSDPublisher::EndPublication(void)
0x180001c53  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c5a  mov     ebx, eax
0x180001c5c  test    eax, eax
0x180001c5e  jnz     short loc_180001C6B
0x180001c60  cmp     byte ptr [rcx+19h], 4
0x180001c64  jmp     short loc_180001C71
0x180001c66  mov     ebx, 1
0x180001c6b  xor     eax, eax
0x180001c6d  cmp     byte ptr [rcx+19h], 2
0x180001c71  setnb   al
0x180001c74  cmp     rcx, rsi
0x180001c77  jz      short loc_180001C9B
0x180001c79  test    eax, eax
0x180001c7b  jz      short loc_180001C9B
0x180001c7d  mov     rcx, [rcx+10h]
0x180001c81  lea     r8, WPP_dca0bca380213f5562de9c342e06f597_Traceguids
0x180001c88  mov     edx, 0Fh
0x180001c8d  mov     [rsp+38h+var_10], ebx
0x180001c91  mov     [rsp+38h+var_18], rdi
0x180001c96  call    WPP_SF_sqd
0x180001c9b  mov     rsi, [rsp+38h+arg_8]
0x180001ca0  mov     eax, ebx
0x180001ca2  mov     rbx, [rsp+38h+arg_0]
0x180001ca7  add     rsp, 30h
0x180001cab  pop     rdi
0x180001cac  retn
```
