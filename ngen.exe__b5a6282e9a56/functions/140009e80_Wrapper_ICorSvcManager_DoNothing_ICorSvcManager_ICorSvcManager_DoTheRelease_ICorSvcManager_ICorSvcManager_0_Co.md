# Wrapper<ICorSvcManager *,&DoNothing<ICorSvcManager *>(ICorSvcManager *),&DoTheRelease<ICorSvcManager>(ICorSvcManager *),0,&CompareDefault<ICorSvcManager *>(ICorSvcManager *,ICorSvcManager *),2,1>::~Wrapper<ICorSvcManager *,&DoNothing<ICorSvcManager *>(ICorSvcManager *),&DoTheRelease<ICorSvcManager>(ICorSvcManager *),0,&CompareDefault<ICorSvcManager *>(ICorSvcManager *,ICorSvcManager *),2,1>(void)

- ea: `0x140009e80`
- end: `0x140009eb2`
- name: `??1?$Wrapper@PEAUICorSvcManager@@$1??$DoNothing@PEAUICorSvcManager@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcManager@@@@YAX0@Z$0A@$1??$CompareDefault@PEAUICorSvcManager@@@@YAH00@Z$01$00@@QEAA@XZ`
- size: `50`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `19`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400143d3`
- `0x140014429`
- `0x140014473`
- `0x140014497`
- `0x1400144bb`
- `0x1400144df`
- `0x140014503`
- `0x140014527`
- `0x140014571`
- `0x14001462d`
- `0x1400149fd`
- `0x140014a53`
- `0x140014aa9`
- `0x140014caf`
- `0x140014e03`
- `0x140014e27`
- `0x14001503f`
- `0x1400150c1`
- `0x140015595`

## callees

- `0x140009e80`
- `0x140013f30`

## pseudocode

```c
__int64 __fastcall Wrapper<ICorSvcManager *,&void DoNothing<ICorSvcManager *>(ICorSvcManager *),&void DoTheRelease<ICorSvcManager>(ICorSvcManager *),0,&int CompareDefault<ICorSvcManager *>(ICorSvcManager *,ICorSvcManager *),2,1>::~Wrapper<ICorSvcManager *,&void DoNothing<ICorSvcManager *>(ICorSvcManager *),&void DoTheRelease<ICorSvcManager>(ICorSvcManager *),0,&int CompareDefault<ICorSvcManager *>(ICorSvcManager *,ICorSvcManager *),2,1>(
        __int64 *a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  if ( *((_DWORD *)a1 + 2) )
  {
    v2 = *a1;
    if ( v2 )
      result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_DWORD *)a1 + 2) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140009e80  mov     [rsp+arg_0], rcx
0x140009e85  push    rbx
0x140009e86  sub     rsp, 20h
0x140009e8a  mov     rbx, rcx
0x140009e8d  cmp     dword ptr [rcx+8], 0
0x140009e91  jz      short loc_140009EAC
0x140009e93  mov     rcx, [rcx]
0x140009e96  test    rcx, rcx
0x140009e99  jz      short loc_140009EA8
0x140009e9b  mov     rax, [rcx]
0x140009e9e  mov     rax, [rax+10h]
0x140009ea2  call    cs:__guard_dispatch_icall_fptr
0x140009ea8  and     dword ptr [rbx+8], 0
0x140009eac  add     rsp, 20h
0x140009eb0  pop     rbx
0x140009eb1  retn
```
