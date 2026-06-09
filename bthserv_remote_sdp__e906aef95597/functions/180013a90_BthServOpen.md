# BthServOpen

- ea: `0x180013a90`
- end: `0x180013c03`
- name: `BthServOpen`
- size: `371`
- prototype: `unsigned int __fastcall(__int64, _QWORD *, _DWORD *, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x18000270c`
- `0x180011f90`
- `0x180011fd0`
- `0x180012004`
- `0x180012f8c`
- `0x180013a90`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180013bbb`
- `RPCRT4!RpcRevertToSelf` at `0x180013bbb`
- `RPCRT4!RpcImpersonateClient` at `0x180013b28`
- `RPCRT4!RpcImpersonateClient` at `0x180013b28`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180013bac`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180013bac`

## pseudocode

```c
unsigned int __fastcall BthServOpen(__int64 a1, _QWORD *a2, _DWORD *a3, __int64 a4)
{
  unsigned int result; // eax
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  char v10; // bl
  HANDLE v11; // rbx
  __int64 v12; // [rsp+50h] [rbp-18h] BYREF

  result = BthServRpcAuthenticate(&v12);
  if ( !result )
  {
    v8 = MIDL_user_allocate(0x68u);
    v9 = v8;
    if ( v8 )
    {
      memset_0(v8, 0, 0x68u);
      *v9 = a4;
      v9[3] = v9 + 2;
      v10 = 1;
      v9[2] = v9 + 2;
      v9[5] = v9 + 4;
      v9[4] = v9 + 4;
      v9[8] = v9 + 7;
      v9[7] = v9 + 7;
      v9[10] = v9 + 9;
      v9[9] = v9 + 9;
      *((_DWORD *)v9 + 12) = 0;
      *((_DWORD *)v9 + 22) = 1;
      if ( RpcImpersonateClient(0) )
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          v10 = 0;
        if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v10,
            WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
            *((_QWORD *)WPP_GLOBAL_Control + 5));
        SdpFreePool(v9);
        *a2 = 0;
        *a3 = -2147024891;
      }
      else
      {
        v11 = OpenProcess(0x40u, 0, *(_DWORD *)v9);
        RpcRevertToSelf();
        if ( v11 )
        {
          v9[1] = v11;
          *a2 = v9;
          *a3 = 0;
        }
        else
        {
          SdpFreePool(v9);
          *a2 = 0;
          *a3 = -2147024736;
        }
      }
    }
    else
    {
      *a2 = 0;
      *a3 = -2147024882;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180013a90  mov     rax, rsp
0x180013a93  mov     [rax+8], rbx
0x180013a97  mov     [rax+10h], rsi
0x180013a9b  mov     [rax+18h], rdi
0x180013a9f  push    r14
0x180013aa1  sub     rsp, 60h
0x180013aa5  lea     rcx, [rax-18h]; void *
0x180013aa9  mov     rbx, r9
0x180013aac  mov     rsi, r8
0x180013aaf  mov     r14, rdx
0x180013ab2  call    ?BthServRpcAuthenticate@@YAKPEAX@Z; BthServRpcAuthenticate(void *)
0x180013ab7  test    eax, eax
0x180013ab9  jnz     loc_180013BEB
0x180013abf  lea     ecx, [rax+68h]; size
0x180013ac2  call    MIDL_user_allocate
0x180013ac7  mov     rdi, rax
0x180013aca  test    rax, rax
0x180013acd  jnz     short loc_180013ADD
0x180013acf  and     [r14], rax
0x180013ad2  mov     dword ptr [rsi], 8007000Eh
0x180013ad8  jmp     loc_180013BE9
0x180013add  xor     edx, edx; Val
0x180013adf  mov     rcx, rdi; void *
0x180013ae2  lea     r8d, [rdx+68h]; Size
0x180013ae6  call    memset_0
0x180013aeb  mov     [rdi], rbx
0x180013aee  lea     rax, [rdi+10h]
0x180013af2  mov     [rax+8], rax
0x180013af6  mov     ebx, 1
0x180013afb  mov     [rax], rax
0x180013afe  xor     ecx, ecx; BindingHandle
0x180013b00  lea     rax, [rdi+20h]
0x180013b04  mov     [rax+8], rax
0x180013b08  mov     [rax], rax
0x180013b0b  lea     rax, [rdi+38h]
0x180013b0f  mov     [rax+8], rax
0x180013b13  mov     [rax], rax
0x180013b16  lea     rax, [rdi+48h]
0x180013b1a  mov     [rax+8], rax
0x180013b1e  mov     [rax], rax
0x180013b21  and     dword ptr [rdi+30h], 0
0x180013b25  mov     [rdi+58h], ebx
0x180013b28  call    cs:__imp_RpcImpersonateClient
0x180013b2f  nop     dword ptr [rax+rax+00h]
0x180013b34  test    eax, eax
0x180013b36  jz      short loc_180013BA4
0x180013b38  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b3f  lea     rax, WPP_GLOBAL_Control
0x180013b46  cmp     rcx, rax
0x180013b49  jz      short loc_180013B51
0x180013b4b  cmp     byte ptr [rcx+19h], 4
0x180013b4f  jnb     short loc_180013B53
0x180013b51  xor     bl, bl
0x180013b53  lea     rax, WPP_RECORDER_INITIALIZED
0x180013b5a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180013b61  setnz   r8b
0x180013b65  test    bl, bl
0x180013b67  jnz     short loc_180013B6E
0x180013b69  test    r8b, r8b
0x180013b6c  jz      short loc_180013B90
0x180013b6e  mov     r9, [rcx+28h]
0x180013b72  lea     rax, WPP_efb6cd7e54bb348036d84fdff4bfab53_Traceguids
0x180013b79  mov     rcx, [rcx+10h]
0x180013b7d  mov     dl, bl
0x180013b7f  mov     [rsp+68h+var_30], rax
0x180013b84  mov     [rsp+68h+var_38], 0Ch
0x180013b8b  call    WPP_RECORDER_AND_TRACE_SF_s
0x180013b90  mov     rcx, rdi
0x180013b93  call    SdpFreePool
0x180013b98  and     qword ptr [r14], 0
0x180013b9c  mov     dword ptr [rsi], 80070005h
0x180013ba2  jmp     short loc_180013BE9
0x180013ba4  mov     r8d, [rdi]; dwProcessId
0x180013ba7  xor     edx, edx; bInheritHandle
0x180013ba9  lea     ecx, [rdx+40h]; dwDesiredAccess
0x180013bac  call    cs:__imp_OpenProcess
0x180013bb3  nop     dword ptr [rax+rax+00h]
0x180013bb8  mov     rbx, rax
0x180013bbb  call    cs:__imp_RpcRevertToSelf
0x180013bc2  nop     dword ptr [rax+rax+00h]
0x180013bc7  test    rbx, rbx
0x180013bca  jnz     short loc_180013BDF
0x180013bcc  mov     rcx, rdi
0x180013bcf  call    SdpFreePool
0x180013bd4  and     [r14], rbx
0x180013bd7  mov     dword ptr [rsi], 800700A0h
0x180013bdd  jmp     short loc_180013BE9
0x180013bdf  mov     [rdi+8], rbx
0x180013be3  mov     [r14], rdi
0x180013be6  and     dword ptr [rsi], 0
0x180013be9  xor     eax, eax
0x180013beb  lea     r11, [rsp+68h+var_8]
0x180013bf0  mov     rbx, [r11+10h]
0x180013bf4  mov     rsi, [r11+18h]
0x180013bf8  mov     rdi, [r11+20h]
0x180013bfc  mov     rsp, r11
0x180013bff  pop     r14
0x180013c01  retn
```
