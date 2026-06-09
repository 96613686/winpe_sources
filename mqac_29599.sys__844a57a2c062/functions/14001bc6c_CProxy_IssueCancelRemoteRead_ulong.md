# CProxy::IssueCancelRemoteRead(ulong)

- ea: `0x14001bc6c`
- end: `0x14001bcaa`
- name: `?IssueCancelRemoteRead@CProxy@@AEBAJK@Z`
- size: `62`
- prototype: `__int64 __fastcall(CProxy *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001b700`

## callees

- `0x14001b114`

## pseudocode

```c
__int64 __fastcall CProxy::IssueCancelRemoteRead(CProxy *this, int a2)
{
  __int64 v2; // rax
  _BYTE v4[16]; // [rsp+20h] [rbp-F8h] BYREF
  int v5; // [rsp+30h] [rbp-E8h]
  __int64 v6; // [rsp+38h] [rbp-E0h]
  int v7; // [rsp+40h] [rbp-D8h]

  v6 = *((_QWORD *)this + 19);
  v2 = *((_QWORD *)this + 8);
  v7 = a2;
  v5 = 5;
  return CQMInterface::ProcessRequest((CQMInterface *)(*(_QWORD *)(v2 + 64) + 72LL), (const struct CACRequest *)v4);
}

```

## disassembly

```asm
0x14001bc6c  sub     rsp, 118h
0x14001bc73  mov     rax, [rcx+98h]
0x14001bc7a  mov     [rsp+118h+var_E0], rax
0x14001bc7f  mov     rax, [rcx+40h]
0x14001bc83  mov     [rsp+118h+var_D8], edx
0x14001bc87  lea     rdx, [rsp+118h+var_F8]; struct CACRequest *
0x14001bc8c  mov     [rsp+118h+var_E8], 5
0x14001bc94  mov     rcx, [rax+40h]
0x14001bc98  add     rcx, 48h ; 'H'; this
0x14001bc9c  call    ?ProcessRequest@CQMInterface@@QEAAJAEBVCACRequest@@@Z; CQMInterface::ProcessRequest(CACRequest const &)
0x14001bca1  add     rsp, 118h
0x14001bca8  retn
```
