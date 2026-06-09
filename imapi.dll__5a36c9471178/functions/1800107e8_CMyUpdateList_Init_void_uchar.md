# CMyUpdateList::Init(void *,uchar *)

- ea: `0x1800107e8`
- end: `0x1800108a2`
- name: `?Init@CMyUpdateList@@QEAAEPEAXPEAE@Z`
- size: `186`
- prototype: `unsigned __int8 __fastcall(CMyUpdateList *__hidden this, void *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000c4a8`

## callees

- `0x180007bac`
- `0x18000e804`
- `0x1800107e8`

## pseudocode

```c
char __fastcall CMyUpdateList::Init(CMyUpdateList *this, void *a2, unsigned __int8 *a3)
{
  char v3; // di

  v3 = 0;
  if ( _InterlockedExchange((volatile __int32 *)this + 2, 1) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_51141d96add4351c86cdeea4487a7041_Traceguids);
  }
  else if ( *((_DWORD *)this + 3) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        11,
        WPP_51141d96add4351c86cdeea4487a7041_Traceguids,
        *((_QWORD *)this + 18),
        a2);
  }
  else
  {
    *((_QWORD *)this + 18) = a2;
    v3 = 1;
    *((_QWORD *)this + 19) = a3;
    *((_DWORD *)this + 3) = 1;
  }
  *((_DWORD *)this + 2) = 0;
  return v3;
}

```

## disassembly

```asm
0x1800107e8  mov     [rsp+arg_0], rbx
0x1800107ed  push    rdi
0x1800107ee  sub     rsp, 30h
0x1800107f2  mov     r9, rdx
0x1800107f5  xor     dil, dil
0x1800107f8  mov     edx, 1
0x1800107fd  mov     rbx, rcx
0x180010800  mov     eax, edx
0x180010802  xchg    eax, [rcx+8]
0x180010805  test    eax, eax
0x180010807  jz      short loc_180010838
0x180010809  mov     rcx, cs:WPP_GLOBAL_Control
0x180010810  lea     rax, WPP_GLOBAL_Control
0x180010817  cmp     rcx, rax
0x18001081a  jz      short loc_18001088D
0x18001081c  test    [rcx+44h], dl
0x18001081f  jz      short loc_18001088D
0x180010821  mov     rcx, [rcx+38h]
0x180010825  lea     r8, WPP_51141d96add4351c86cdeea4487a7041_Traceguids
0x18001082c  mov     edx, 0Ah
0x180010831  call    WPP_SF_
0x180010836  jmp     short loc_18001088D
0x180010838  cmp     dword ptr [rcx+0Ch], 0
0x18001083c  jz      short loc_180010879
0x18001083e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010845  lea     rax, WPP_GLOBAL_Control
0x18001084c  cmp     rcx, rax
0x18001084f  jz      short loc_18001088D
0x180010851  test    [rcx+44h], dl
0x180010854  jz      short loc_18001088D
0x180010856  mov     rcx, [rcx+38h]
0x18001085a  lea     r8, WPP_51141d96add4351c86cdeea4487a7041_Traceguids
0x180010861  mov     [rsp+38h+var_18], r9
0x180010866  mov     edx, 0Bh
0x18001086b  mov     r9, [rbx+90h]
0x180010872  call    WPP_SF_qq
0x180010877  jmp     short loc_18001088D
0x180010879  mov     [rcx+90h], r9
0x180010880  mov     dil, dl
0x180010883  mov     [rcx+98h], r8
0x18001088a  mov     [rcx+0Ch], edx
0x18001088d  mov     dword ptr [rbx+8], 0
0x180010894  mov     al, dil
0x180010897  mov     rbx, [rsp+38h+arg_0]
0x18001089c  add     rsp, 30h
0x1800108a0  pop     rdi
0x1800108a1  retn
```
