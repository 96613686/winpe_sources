# CMSDiscRecorderObj::OpenExclusive(void)

- ea: `0x18000fd40`
- end: `0x18000fe19`
- name: `?OpenExclusive@CMSDiscRecorderObj@@UEAAJXZ`
- size: `217`
- prototype: `__int64 __fastcall(CMSDiscRecorderObj *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180007d40`
- `0x180007d80`
- `0x18000fd40`
- `0x1800140ac`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000fdcb`
- `KERNEL32!LeaveCriticalSection` at `0x18000fdcb`
- `KERNEL32!EnterCriticalSection` at `0x18000fd8a`
- `KERNEL32!EnterCriticalSection` at `0x18000fd8a`

## pseudocode

```c
__int64 __fastcall CMSDiscRecorderObj::OpenExclusive(CMSDiscRecorderObj *this)
{
  int v2; // edi

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 35, WPP_d26c5e076d373d9f44765f33302aa61b_Traceguids, (char *)this - 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  if ( *((_BYTE *)this + 140) )
  {
    if ( *((_BYTE *)this + 142) )
    {
      v2 = -2147220974;
    }
    else
    {
      v2 = WriterOpenExclusive((_QWORD *)this + 9, 1);
      if ( v2 >= 0 )
        *((_BYTE *)this + 142) = 1;
    }
  }
  else
  {
    v2 = -2147220980;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  if ( *((_DWORD *)this + 16) )
    v2 = -2147220973;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      36,
      WPP_d26c5e076d373d9f44765f33302aa61b_Traceguids,
      (char *)this - 8,
      v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000fd40  push    rbx
0x18000fd42  push    rbp
0x18000fd43  push    rsi
0x18000fd44  push    rdi
0x18000fd45  push    r15
0x18000fd47  sub     rsp, 30h
0x18000fd4b  mov     rbx, rcx
0x18000fd4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd55  lea     r15, WPP_GLOBAL_Control
0x18000fd5c  cmp     rcx, r15
0x18000fd5f  jz      short loc_18000FD80
0x18000fd61  test    byte ptr [rcx+44h], 1
0x18000fd65  jz      short loc_18000FD80
0x18000fd67  mov     rcx, [rcx+38h]
0x18000fd6b  lea     r9, [rbx-8]
0x18000fd6f  mov     edx, 23h ; '#'
0x18000fd74  lea     r8, WPP_d26c5e076d373d9f44765f33302aa61b_Traceguids
0x18000fd7b  call    WPP_SF_q
0x18000fd80  lea     rbp, [rbx+90h]
0x18000fd87  mov     rcx, rbp; lpCriticalSection
0x18000fd8a  call    cs:__imp_EnterCriticalSection
0x18000fd90  cmp     byte ptr [rbx+8Ch], 0
0x18000fd97  jnz     short loc_18000FDA0
0x18000fd99  mov     edi, 8004020Ch
0x18000fd9e  jmp     short loc_18000FDC8
0x18000fda0  cmp     byte ptr [rbx+8Eh], 0
0x18000fda7  jz      short loc_18000FDB0
0x18000fda9  mov     edi, 80040212h
0x18000fdae  jmp     short loc_18000FDC8
0x18000fdb0  lea     rcx, [rbx+48h]
0x18000fdb4  mov     dl, 1
0x18000fdb6  call    WriterOpenExclusive
0x18000fdbb  mov     edi, eax
0x18000fdbd  test    eax, eax
0x18000fdbf  js      short loc_18000FDC8
0x18000fdc1  mov     byte ptr [rbx+8Eh], 1
0x18000fdc8  mov     rcx, rbp; lpCriticalSection
0x18000fdcb  call    cs:__imp_LeaveCriticalSection
0x18000fdd1  cmp     dword ptr [rbx+40h], 0
0x18000fdd5  mov     eax, 80040213h
0x18000fdda  cmovnz  edi, eax
0x18000fddd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fde4  cmp     rcx, r15
0x18000fde7  jz      short loc_18000FE0C
0x18000fde9  test    byte ptr [rcx+44h], 1
0x18000fded  jz      short loc_18000FE0C
0x18000fdef  mov     rcx, [rcx+38h]
0x18000fdf3  lea     r9, [rbx-8]
0x18000fdf7  mov     edx, 24h ; '$'
0x18000fdfc  mov     [rsp+58h+var_38], edi
0x18000fe00  lea     r8, WPP_d26c5e076d373d9f44765f33302aa61b_Traceguids
0x18000fe07  call    WPP_SF_qD
0x18000fe0c  mov     eax, edi
0x18000fe0e  add     rsp, 30h
0x18000fe12  pop     r15
0x18000fe14  pop     rdi
0x18000fe15  pop     rsi
0x18000fe16  pop     rbp
0x18000fe17  pop     rbx
0x18000fe18  retn
```
