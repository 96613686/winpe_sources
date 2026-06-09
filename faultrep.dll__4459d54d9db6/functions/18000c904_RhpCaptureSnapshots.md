# RhpCaptureSnapshots

- ea: `0x18000c904`
- end: `0x18000ca2b`
- name: `RhpCaptureSnapshots`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c44c`

## callees

- `0x180003474`
- `0x18000c904`

## import_xrefs

- `ntdll!NtClose` at `0x18000ca03`
- `ntdll!NtClose` at `0x18000ca03`
- `ntdll!PssNtCaptureSnapshot` at `0x18000c9f5`
- `ntdll!PssNtCaptureSnapshot` at `0x18000c9f5`
- `ntdll!NtOpenProcess` at `0x18000c9c6`
- `ntdll!NtOpenProcess` at `0x18000c9c6`
- `ntdll!RtlQueryResourcePolicy` at `0x18000c98b`
- `ntdll!RtlQueryResourcePolicy` at `0x18000c98b`

## pseudocode

```c
NTSTATUS __fastcall RhpCaptureSnapshots(_QWORD *a1, _OWORD *a2, __m128i *a3, __int64 a4, int *a5)
{
  NTSTATUS result; // eax
  __m128i si128; // xmm1
  int *v10; // rbx
  void *v11; // rdx
  int v12; // eax
  void *v13; // rcx
  int v14; // ebx
  void *ProcessHandle; // [rsp+20h] [rbp-20h] BYREF
  __int64 v16; // [rsp+28h] [rbp-18h] BYREF
  _CLIENT_ID ClientId; // [rsp+30h] [rbp-10h] BYREF
  int v18; // [rsp+78h] [rbp+38h] BYREF

  ProcessHandle = 0;
  v16 = 0;
  v18 = 0;
  ClientId = 0;
  result = (unsigned int)memset_0(a1, 0, 0x80u);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v10 = a5;
  *a2 = 0;
  *a3 = si128;
  a3[1] = si128;
  a3[2] = si128;
  a3[3] = si128;
  if ( *v10 )
  {
    result = RtlQueryResourcePolicy(0, 0, &v18, 4);
    if ( result < 0 || v18 > 10 )
    {
      ClientId.UniqueProcess = (HANDLE)*v10;
      ClientId.UniqueThread = 0;
      result = NtOpenProcess(&ProcessHandle, 0x4D0u, (POBJECT_ATTRIBUTES)&ObjectAttributes, &ClientId);
      a3->m128i_i32[0] = result;
      if ( result >= 0 )
      {
        v11 = ProcessHandle;
        *a1 = 0;
        v16 = 0;
        v12 = PssNtCaptureSnapshot(&v16, v11, 3690994175LL, 1048607);
        v13 = ProcessHandle;
        v14 = v12;
        a3->m128i_i32[0] = v12;
        result = NtClose(v13);
        if ( v14 >= 0 )
        {
          result = v16;
          *a1 = v16;
          *(_BYTE *)a2 = 8;
        }
      }
    }
    else
    {
      a3->m128i_i32[0] = -1073741801;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c904  mov     [rsp-18h+arg_0], rbx
0x18000c909  mov     [rsp-18h+arg_8], rsi
0x18000c90e  mov     [rsp-18h+arg_18], r9d
0x18000c913  push    rbp
0x18000c914  push    rdi
0x18000c915  push    r14
0x18000c917  mov     rbp, rsp
0x18000c91a  sub     rsp, 40h
0x18000c91e  mov     rdi, r8
0x18000c921  mov     [rbp+ProcessHandle], 0
0x18000c929  mov     r14, rdx
0x18000c92c  mov     [rbp+var_18], 0
0x18000c934  xorps   xmm0, xmm0
0x18000c937  mov     [rbp+arg_18], 0
0x18000c93e  xor     edx, edx; Val
0x18000c940  mov     r8d, 80h; Size
0x18000c946  movups  xmmword ptr [rbp+ClientId.UniqueProcess], xmm0
0x18000c94a  mov     rsi, rcx
0x18000c94d  call    memset_0
0x18000c952  movdqa  xmm1, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000c95a  xorps   xmm0, xmm0
0x18000c95d  mov     rbx, [rbp+arg_20]
0x18000c961  movups  xmmword ptr [r14], xmm0
0x18000c965  movups  xmmword ptr [rdi], xmm1
0x18000c968  movups  xmmword ptr [rdi+10h], xmm1
0x18000c96c  movups  xmmword ptr [rdi+20h], xmm1
0x18000c970  movups  xmmword ptr [rdi+30h], xmm1
0x18000c974  cmp     dword ptr [rbx], 0
0x18000c977  jz      loc_18000CA18
0x18000c97d  mov     r9d, 4
0x18000c983  lea     r8, [rbp+arg_18]
0x18000c987  xor     edx, edx
0x18000c989  xor     ecx, ecx
0x18000c98b  call    cs:__imp_RtlQueryResourcePolicy
0x18000c991  test    eax, eax
0x18000c993  js      short loc_18000C9A3
0x18000c995  cmp     [rbp+arg_18], 0Ah
0x18000c999  jg      short loc_18000C9A3
0x18000c99b  mov     dword ptr [rdi], 0C0000017h
0x18000c9a1  jmp     short loc_18000CA18
0x18000c9a3  movsxd  rax, dword ptr [rbx]
0x18000c9a6  lea     r9, [rbp+ClientId]; ClientId
0x18000c9aa  lea     r8, ObjectAttributes; ObjectAttributes
0x18000c9b1  mov     [rbp+ClientId.UniqueProcess], rax
0x18000c9b5  mov     edx, 4D0h; DesiredAccess
0x18000c9ba  mov     [rbp+ClientId.UniqueThread], 0
0x18000c9c2  lea     rcx, [rbp+ProcessHandle]; ProcessHandle
0x18000c9c6  call    cs:__imp_NtOpenProcess
0x18000c9cc  mov     [rdi], eax
0x18000c9ce  test    eax, eax
0x18000c9d0  js      short loc_18000CA18
0x18000c9d2  mov     rdx, [rbp+ProcessHandle]
0x18000c9d6  lea     rcx, [rbp+var_18]
0x18000c9da  mov     r9d, 10001Fh
0x18000c9e0  mov     qword ptr [rsi], 0
0x18000c9e7  mov     r8d, 0DC0019FFh
0x18000c9ed  mov     [rbp+var_18], 0
0x18000c9f5  call    cs:__imp_PssNtCaptureSnapshot
0x18000c9fb  mov     rcx, [rbp+ProcessHandle]; Handle
0x18000c9ff  mov     ebx, eax
0x18000ca01  mov     [rdi], eax
0x18000ca03  call    cs:__imp_NtClose
0x18000ca09  test    ebx, ebx
0x18000ca0b  js      short loc_18000CA18
0x18000ca0d  mov     rax, [rbp+var_18]
0x18000ca11  mov     [rsi], rax
0x18000ca14  mov     byte ptr [r14], 8
0x18000ca18  mov     rbx, [rsp+40h+arg_0]
0x18000ca1d  mov     rsi, [rsp+40h+arg_8]
0x18000ca22  add     rsp, 40h
0x18000ca26  pop     r14
0x18000ca28  pop     rdi
0x18000ca29  pop     rbp
0x18000ca2a  retn
```
