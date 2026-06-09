# Marshal::Details::ParseJsonSimple(Marshal::JsonParser &,Marshal::Details::Tag<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>)

- ea: `0x14001ae48`
- end: `0x14001aeb5`
- name: `?ParseJsonSimple@Details@Marshal@@YA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@AEAVJsonParser@2@U?$Tag@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@12@@Z`
- size: `109`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, char)`
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000fe4c`
- `0x14000feb8`
- `0x14000ff24`
- `0x14000ff90`
- `0x14000fffc`
- `0x140010068`
- `0x1400100d4`
- `0x140010140`
- `0x1400101ac`

## callees

- `0x140002d4e`
- `0x14001ae48`
- `0x14001b484`
- `0x14001b8a8`

## pseudocode

```c
_QWORD *__fastcall Marshal::Details::ParseJsonSimple(_QWORD *a1, __int64 a2, char a3)
{
  _QWORD *v5; // rax
  _QWORD *v6; // rcx
  _QWORD *result; // rax
  int pExceptionObject; // [rsp+40h] [rbp+18h] BYREF

  LOBYTE(pExceptionObject) = a3;
  if ( (unsigned int)Marshal::JsonParser::PeekValueType(a2) != 1 )
  {
    pExceptionObject = 7;
    throw (Marshal::UnmarshalError *)&pExceptionObject;
  }
  v5 = (_QWORD *)Marshal::JsonParser::ParseString(a2);
  if ( v5[3] <= 7u )
    v6 = v5;
  else
    v6 = (_QWORD *)*v5;
  a1[1] = v5[2];
  result = a1;
  *a1 = v6;
  return result;
}

```

## disassembly

```asm
0x14001ae48  mov     [rsp+arg_0], rbx
0x14001ae4d  mov     byte ptr [rsp+pExceptionObject], r8b
0x14001ae52  push    rdi
0x14001ae53  sub     rsp, 20h
0x14001ae57  mov     rbx, rcx
0x14001ae5a  mov     rdi, rdx
0x14001ae5d  mov     rcx, rdx
0x14001ae60  call    ?PeekValueType@JsonParser@Marshal@@QEAA?AW4ValueType@12@XZ; Marshal::JsonParser::PeekValueType(void)
0x14001ae65  cmp     eax, 1
0x14001ae68  jnz     short loc_14001AE9B
0x14001ae6a  mov     rcx, rdi
0x14001ae6d  call    ?ParseString@JsonParser@Marshal@@QEAAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Marshal::JsonParser::ParseString(void)
0x14001ae72  cmp     qword ptr [rax+18h], 7
0x14001ae77  jbe     short loc_14001AE7E
0x14001ae79  mov     rcx, [rax]
0x14001ae7c  jmp     short loc_14001AE81
0x14001ae7e  mov     rcx, rax
0x14001ae81  mov     rax, [rax+10h]
0x14001ae85  mov     [rbx+8], rax
0x14001ae89  mov     rax, rbx
0x14001ae8c  mov     [rbx], rcx
0x14001ae8f  mov     rbx, [rsp+28h+arg_0]
0x14001ae94  add     rsp, 20h
0x14001ae98  pop     rdi
0x14001ae99  retn
0x14001ae9b  lea     rdx, _TI1?AW4UnmarshalError@Marshal@@; pThrowInfo
0x14001aea2  mov     [rsp+28h+pExceptionObject], 7
0x14001aeaa  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14001aeaf  call    _CxxThrowException_0
```
