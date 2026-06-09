# Dock::IsAutoConnectDisallowed(void)

- ea: `0x180012288`
- end: `0x180012329`
- name: `?IsAutoConnectDisallowed@Dock@@AEBA_NXZ`
- size: `161`
- prototype: `char __fastcall(Dock *this)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180011470`
- `0x180011acc`
- `0x180012330`
- `0x180012788`
- `0x180012b34`
- `0x180012ba0`

## callees

- `0x180012288`
- `0x1800134b4`

## pseudocode

```c
char __fastcall Dock::IsAutoConnectDisallowed(Dock *this)
{
  char v2; // di

  v2 = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qSllll(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *((unsigned __int8 *)this + 1744),
      *((unsigned __int8 *)this + 587),
      (_DWORD)this,
      (__int64)this,
      *((_BYTE *)this + 587),
      *((_DWORD *)this + 283),
      *((_BYTE *)this + 1744),
      *((_DWORD *)this + 726));
  }
  if ( (!*((_BYTE *)this + 587) || *((_DWORD *)this + 283) != 1)
    && (!*((_BYTE *)this + 1744) || *((_DWORD *)this + 726) != 1) )
  {
    return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x180012288  mov     [rsp+arg_0], rbx
0x18001228d  push    rdi
0x18001228e  sub     rsp, 50h
0x180012292  mov     rbx, rcx
0x180012295  mov     rcx, cs:WPP_GLOBAL_Control
0x18001229c  lea     rax, WPP_GLOBAL_Control
0x1800122a3  mov     edi, 1
0x1800122a8  cmp     rcx, rax
0x1800122ab  jz      short loc_1800122F6
0x1800122ad  cmp     byte ptr [rcx+19h], 4
0x1800122b1  jb      short loc_1800122F6
0x1800122b3  test    [rcx+1Ch], dil
0x1800122b7  jz      short loc_1800122F6
0x1800122b9  mov     eax, [rbx+0B58h]
0x1800122bf  mov     r9, rbx
0x1800122c2  movzx   edx, byte ptr [rbx+6D0h]
0x1800122c9  movzx   r8d, byte ptr [rbx+24Bh]
0x1800122d1  mov     rcx, [rcx+10h]
0x1800122d5  mov     [rsp+58h+var_18], eax
0x1800122d9  mov     eax, [rbx+46Ch]
0x1800122df  mov     [rsp+58h+var_20], edx
0x1800122e3  mov     [rsp+58h+var_28], eax
0x1800122e7  mov     [rsp+58h+var_30], r8d
0x1800122ec  mov     [rsp+58h+var_38], rbx
0x1800122f1  call    WPP_SF_qSllll
0x1800122f6  cmp     byte ptr [rbx+24Bh], 0
0x1800122fd  jz      short loc_180012307
0x1800122ff  cmp     [rbx+46Ch], edi
0x180012305  jz      short loc_18001231B
0x180012307  cmp     byte ptr [rbx+6D0h], 0
0x18001230e  jz      short loc_180012318
0x180012310  cmp     [rbx+0B58h], edi
0x180012316  jz      short loc_18001231B
0x180012318  xor     dil, dil
0x18001231b  mov     rbx, [rsp+58h+arg_0]
0x180012320  mov     al, dil
0x180012323  add     rsp, 50h
0x180012327  pop     rdi
0x180012328  retn
```
