# Wrapper<Exception *,&DoNothing<Exception *>(Exception *),&Delete<Exception>(Exception *),0,&CompareDefault<Exception *>(Exception *,Exception *),2,1>::~Wrapper<Exception *,&DoNothing<Exception *>(Exception *),&Delete<Exception>(Exception *),0,&CompareDefault<Exception *>(Exception *,Exception *),2,1>(void)

- ea: `0x14000ea30`
- end: `0x14000ea66`
- name: `??1?$Wrapper@PEAVException@@$1??$DoNothing@PEAVException@@@@YAXPEAV1@@Z$1??$Delete@VException@@@@YAX0@Z$0A@$1??$CompareDefault@PEAVException@@@@YAH00@Z$01$00@@QEAA@XZ`
- size: `54`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140015731`
- `0x1400157dc`

## callees

- `0x14000ea30`
- `0x140013f30`

## pseudocode

```c
__int64 __fastcall Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Delete<Exception>(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2,1>::~Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Delete<Exception>(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2,1>(
        __int64 a1)
{
  __int64 (__fastcall ***v2)(_QWORD, __int64); // rcx
  __int64 result; // rax

  if ( *(_DWORD *)(a1 + 8) )
  {
    v2 = *(__int64 (__fastcall ****)(_QWORD, __int64))a1;
    if ( v2 )
      result = (**v2)(v2, 1);
    *(_DWORD *)(a1 + 8) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000ea30  mov     [rsp+arg_0], rcx
0x14000ea35  push    rbx
0x14000ea36  sub     rsp, 20h
0x14000ea3a  mov     rbx, rcx
0x14000ea3d  cmp     dword ptr [rcx+8], 0
0x14000ea41  jz      short loc_14000EA60
0x14000ea43  mov     rcx, [rcx]
0x14000ea46  test    rcx, rcx
0x14000ea49  jz      short loc_14000EA5C
0x14000ea4b  mov     rax, [rcx]
0x14000ea4e  mov     edx, 1
0x14000ea53  mov     rax, [rax]
0x14000ea56  call    cs:__guard_dispatch_icall_fptr
0x14000ea5c  and     dword ptr [rbx+8], 0
0x14000ea60  add     rsp, 20h
0x14000ea64  pop     rbx
0x14000ea65  retn
```
