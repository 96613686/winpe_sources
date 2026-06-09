# std::basic_filebuf<char,std::char_traits<char>>::_Init(_iobuf *,std::basic_filebuf<char,std::char_traits<char>>::_Initfl)

- ea: `0x18000c368`
- end: `0x18000c410`
- name: `?_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z`
- size: `168`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800071dc`
- `0x18000c578`
- `0x18000c748`
- `0x18000ce90`

## callees

- `0x18000c368`

## import_xrefs

- `msvcp_win!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x18000c386`
- `msvcp_win!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x18000c386`
- `msvcp_win!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXPEAPEAD0PEAH001@Z` at `0x18000c3e5`
- `msvcp_win!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXPEAPEAD0PEAH001@Z` at `0x18000c3e5`
- `api-ms-win-crt-private-l1-1-0!_o__get_stream_buffer_pointers` at `0x18000c3be`
- `api-ms-win-crt-private-l1-1-0!_o__get_stream_buffer_pointers` at `0x18000c3be`

## pseudocode

```c
__int64 __fastcall std::filebuf::_Init(__int64 a1, __int64 a2, int a3)
{
  __int64 result; // rax
  __int64 v6; // [rsp+50h] [rbp+8h] BYREF
  __int64 v7; // [rsp+58h] [rbp+10h] BYREF
  __int64 v8; // [rsp+68h] [rbp+20h] BYREF

  *(_BYTE *)(a1 + 113) = 0;
  *(_BYTE *)(a1 + 124) = a3 == 1;
  std::streambuf::_Init();
  if ( a2 )
  {
    v8 = 0;
    v7 = 0;
    v6 = 0;
    _o__get_stream_buffer_pointers(a2, &v8, &v7, &v6);
    std::streambuf::_Init(a1);
  }
  result = `std::filebuf::_Init'::`2'::_Stinit;
  *(_QWORD *)(a1 + 116) = `std::filebuf::_Init'::`2'::_Stinit;
  *(_QWORD *)(a1 + 128) = a2;
  *(_QWORD *)(a1 + 104) = 0;
  return result;
}

```

## disassembly

```asm
0x18000c368  mov     [rsp+arg_10], rbx
0x18000c36d  push    rdi
0x18000c36e  sub     rsp, 40h
0x18000c372  cmp     r8d, 1
0x18000c376  mov     byte ptr [rcx+71h], 0
0x18000c37a  mov     rdi, rdx
0x18000c37d  mov     rbx, rcx
0x18000c380  setz    al
0x18000c383  mov     [rcx+7Ch], al
0x18000c386  call    cs:__imp_?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ; std::streambuf::_Init(void)
0x18000c38c  test    rdi, rdi
0x18000c38f  jz      short loc_18000C3EB
0x18000c391  lea     r9, [rsp+48h+arg_0]
0x18000c396  mov     [rsp+48h+arg_18], 0
0x18000c39f  lea     r8, [rsp+48h+arg_8]
0x18000c3a4  mov     [rsp+48h+arg_8], 0
0x18000c3ad  lea     rdx, [rsp+48h+arg_18]
0x18000c3b2  mov     [rsp+48h+arg_0], 0
0x18000c3bb  mov     rcx, rdi
0x18000c3be  call    cs:__imp__o__get_stream_buffer_pointers
0x18000c3c4  mov     r9, [rsp+48h+arg_0]
0x18000c3c9  mov     rcx, rbx
0x18000c3cc  mov     r8, [rsp+48h+arg_8]
0x18000c3d1  mov     rdx, [rsp+48h+arg_18]
0x18000c3d6  mov     [rsp+48h+var_18], r9
0x18000c3db  mov     [rsp+48h+var_20], r8
0x18000c3e0  mov     [rsp+48h+var_28], rdx
0x18000c3e5  call    cs:__imp_?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXPEAPEAD0PEAH001@Z; std::streambuf::_Init(char * *,char * *,int *,char * *,char * *,int *)
0x18000c3eb  mov     rax, cs:?_Stinit@?1??_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@23@@Z@4U_Mbstatet@@A; _Mbstatet `std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)'::`2'::_Stinit
0x18000c3f2  mov     [rbx+74h], rax
0x18000c3f6  mov     [rbx+80h], rdi
0x18000c3fd  mov     qword ptr [rbx+68h], 0
0x18000c405  mov     rbx, [rsp+48h+arg_10]
0x18000c40a  add     rsp, 40h
0x18000c40e  pop     rdi
0x18000c40f  retn
```
