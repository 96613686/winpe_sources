# CHiveUploadTaskConfigurator::_IsRupUser(void *)

- ea: `0x180002f14`
- end: `0x180002f66`
- name: `?_IsRupUser@CHiveUploadTaskConfigurator@@CAHPEAX@Z`
- size: `82`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800029d0`

## callees

- `0x180002f14`
- `0x180003090`
- `0x18000fca8`

## string_xrefs

- `0x180002f49`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`

## pseudocode

```c
__int64 __fastcall CHiveUploadTaskConfigurator::_IsRupUser(void *a1)
{
  int v1; // eax
  _QWORD v3[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *v5; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v6; // [rsp+48h] [rbp+10h] BYREF

  v5 = a1;
  v6 = 0;
  v3[0] = &v5;
  v3[1] = &v6;
  v1 = lambda_b41eca68381dbaccfa3ca70d9f77ac5d_::operator()(v3);
  if ( v1 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x12A,
      (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
      (const char *)(unsigned int)v1);
  return v6;
}

```

## disassembly

```asm
0x180002f14  mov     r11, rsp
0x180002f17  mov     [r11+8], rcx
0x180002f1b  sub     rsp, 38h
0x180002f1f  lea     rax, [r11+8]
0x180002f23  mov     [rsp+38h+arg_8], 0
0x180002f2b  mov     [r11-18h], rax
0x180002f2f  lea     rcx, [r11-18h]
0x180002f33  lea     rax, [r11+10h]
0x180002f37  mov     [r11-10h], rax
0x180002f3b  call    _lambda_b41eca68381dbaccfa3ca70d9f77ac5d___operator__
0x180002f40  test    eax, eax
0x180002f42  jns     short loc_180002F5D
0x180002f44  mov     rcx, [rsp+38h]; this
0x180002f49  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x180002f50  mov     r9d, eax; char *
0x180002f53  mov     edx, 12Ah; void *
0x180002f58  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180002f5d  mov     eax, [rsp+38h+arg_8]
0x180002f61  add     rsp, 38h
0x180002f65  retn
```
