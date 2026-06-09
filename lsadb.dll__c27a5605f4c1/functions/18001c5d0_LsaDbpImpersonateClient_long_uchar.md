# LsaDbpImpersonateClient(long,uchar *)

- ea: `0x18001c5d0`
- end: `0x18001c619`
- name: `?LsaDbpImpersonateClient@@YAJJPEAE@Z`
- size: `73`
- prototype: `__int64 __fastcall(int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18001c5d0`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x18001c5fd`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001c5fd`
- `SAMSRV!SampDsIsRunning` at `0x18001c5eb`
- `SAMSRV!SampDsIsRunning` at `0x18001c5eb`
- `NTDSA!ImpersonateAnyClient` at `0x18001c5f5`
- `NTDSA!ImpersonateAnyClient` at `0x18001c5f5`

## pseudocode

```c
__int64 __fastcall LsaDbpImpersonateClient(int a1, unsigned __int8 *a2)
{
  RPC_STATUS v4; // eax

  *a2 = 0;
  if ( byte_18004706E )
  {
    if ( (unsigned __int8)SampDsIsRunning() )
    {
      v4 = ImpersonateAnyClient();
      a1 = I_RpcMapWin32Status(v4);
      if ( a1 >= 0 )
        *a2 = 1;
    }
  }
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x18001c5d0  mov     [rsp+arg_0], rbx
0x18001c5d5  push    rdi
0x18001c5d6  sub     rsp, 20h
0x18001c5da  mov     byte ptr [rdx], 0
0x18001c5dd  mov     rdi, rdx
0x18001c5e0  cmp     cs:byte_18004706E, 0
0x18001c5e7  mov     ebx, ecx
0x18001c5e9  jz      short loc_18001C60C
0x18001c5eb  call    cs:__imp_SampDsIsRunning
0x18001c5f1  test    al, al
0x18001c5f3  jz      short loc_18001C60C
0x18001c5f5  call    cs:__imp_ImpersonateAnyClient
0x18001c5fb  mov     ecx, eax; Status
0x18001c5fd  call    cs:__imp_I_RpcMapWin32Status
0x18001c603  mov     ebx, eax
0x18001c605  test    eax, eax
0x18001c607  js      short loc_18001C60C
0x18001c609  mov     byte ptr [rdi], 1
0x18001c60c  mov     eax, ebx
0x18001c60e  mov     rbx, [rsp+28h+arg_0]
0x18001c613  add     rsp, 20h
0x18001c617  pop     rdi
0x18001c618  retn
```
