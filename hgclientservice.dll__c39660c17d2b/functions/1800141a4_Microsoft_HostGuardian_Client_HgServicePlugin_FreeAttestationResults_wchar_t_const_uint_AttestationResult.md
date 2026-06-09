# Microsoft::HostGuardian::Client::HgServicePlugin::FreeAttestationResults(wchar_t * const,uint,AttestationResult *)

- ea: `0x1800141a4`
- end: `0x1800141e7`
- name: `?FreeAttestationResults@HgServicePlugin@Client@HostGuardian@Microsoft@@QEAAJQEA_WIPEAUAttestationResult@@@Z`
- size: `67`
- prototype: `__int64 __fastcall(Microsoft::HostGuardian::Client::HgServicePlugin *this, wchar_t *const, __int64, struct AttestationResult *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c048`
- `0x18000ca70`
- `0x18000dc5c`

## callees

- `0x1800064b4`
- `0x1800141a4`
- `0x180017010`

## string_xrefs

- `0x1800141bc`: `servercommon\base\securehostingservice\common\service\lib\hgserviceplugin.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgServicePlugin::FreeAttestationResults(
        Microsoft::HostGuardian::Client::HgServicePlugin *this,
        wchar_t *const a2,
        __int64 a3,
        struct AttestationResult *a4)
{
  __int64 (*v4)(void); // rax
  __int64 result; // rax
  const char *v6; // r9
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = (__int64 (*)(void))*((_QWORD *)this + 8);
  if ( v4 )
  {
    try
    {
      result = v4();
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x79,
                             (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
                             v6);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x73,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
      (const char *)0x80004001LL,
      v7);
    return 2147500033LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800141a4  sub     rsp, 38h
0x1800141a8  mov     rax, [rcx+40h]
0x1800141ac  test    rax, rax
0x1800141af  jnz     short loc_1800141D2
0x1800141b1  mov     rcx, [rsp+38h]; this
0x1800141b6  mov     r9d, 80004001h; char *
0x1800141bc  lea     r8, aServercommonBa_4; "servercommon\\base\\securehostingservic"...
0x1800141c3  lea     edx, [rax+73h]; void *
0x1800141c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800141cb  mov     eax, 80004001h
0x1800141d0  jmp     short loc_1800141E1
0x1800141d2  mov     rcx, [rcx+10h]
0x1800141d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141db  jmp     short loc_1800141E1
0x1800141dd  mov     eax, [rsp+38h+arg_0]
0x1800141e1  add     rsp, 38h
0x1800141e5  retn
```
