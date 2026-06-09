# CFaxCommon::SetReceiveMode(ushort const *,ulong)

- ea: `0x180005070`
- end: `0x180005160`
- name: `?SetReceiveMode@CFaxCommon@@UEAAJPEBGK@Z`
- size: `240`
- prototype: `__int64 __fastcall(CFaxCommon *this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005070`
- `0x180005a28`

## import_xrefs

- `FXSAPI!FaxSetPortExW` at `0x18000510e`
- `FXSAPI!FaxSetPortExW` at `0x18000510e`
- `FXSAPI!FaxClose` at `0x180005136`
- `FXSAPI!FaxClose` at `0x180005136`
- `FXSAPI!FaxEnumPortsExW` at `0x1800050b9`
- `FXSAPI!FaxEnumPortsExW` at `0x1800050b9`
- `FXSAPI!FaxConnectFaxServerW` at `0x18000509f`
- `FXSAPI!FaxConnectFaxServerW` at `0x18000509f`
- `FXSAPI!FaxFreeBuffer` at `0x180005145`
- `FXSAPI!FaxFreeBuffer` at `0x180005145`
- `KERNEL32!GetLastError` at `0x180005118`
- `KERNEL32!GetLastError` at `0x180005118`

## pseudocode

```c
__int64 __fastcall CFaxCommon::SetReceiveMode(CFaxCommon *this, const unsigned __int16 *a2, int a3)
{
  unsigned int v4; // ebx
  char *v6; // rdi
  __int64 v7; // r8
  char *v8; // rax
  __int64 v9; // rdx
  signed int LastError; // eax
  HANDLE FaxHandle; // [rsp+20h] [rbp-10h] BYREF
  LPVOID Buffer; // [rsp+28h] [rbp-8h] BYREF
  unsigned int v14; // [rsp+68h] [rbp+38h] BYREF

  v4 = 0;
  v14 = 0;
  Buffer = 0;
  FaxHandle = 0;
  if ( FaxConnectFaxServerW(a2, &FaxHandle) )
  {
    if ( !(unsigned int)FaxEnumPortsExW(FaxHandle, &Buffer, &v14) )
      goto LABEL_12;
    if ( v14 )
    {
      v6 = (char *)Buffer;
      v7 = 0;
      while ( 1 )
      {
        v8 = (char *)Buffer + 72 * v7;
        if ( *((_DWORD *)v8 + 10) || *((_DWORD *)v8 + 11) )
          break;
        v7 = (unsigned int)(v7 + 1);
        if ( (unsigned int)v7 >= v14 )
          goto LABEL_10;
      }
      v6 = (char *)Buffer + 72 * v7;
LABEL_10:
      if ( (unsigned int)SetServiceStartupType(a2)
        || (v9 = *((unsigned int *)v6 + 1), *((_DWORD *)v6 + 11) = a3, !(unsigned int)FaxSetPortExW(FaxHandle, v9, v6)) )
      {
LABEL_12:
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  if ( FaxHandle )
    FaxClose(FaxHandle);
  if ( Buffer )
    FaxFreeBuffer(Buffer);
  return v4;
}

```

## disassembly

```asm
0x180005070  mov     [rsp-18h+arg_0], rbx
0x180005075  mov     [rsp-18h+arg_8], rsi
0x18000507a  push    rbp
0x18000507b  push    rdi
0x18000507c  push    r14
0x18000507e  mov     rbp, rsp
0x180005081  sub     rsp, 30h
0x180005085  mov     rsi, rdx
0x180005088  xor     ebx, ebx
0x18000508a  mov     rcx, rsi; MachineName
0x18000508d  mov     [rbp+arg_18], ebx
0x180005090  lea     rdx, [rbp+FaxHandle]; FaxHandle
0x180005094  mov     [rbp+Buffer], rbx
0x180005098  mov     r14d, r8d
0x18000509b  mov     [rbp+FaxHandle], rbx
0x18000509f  call    cs:__imp_FaxConnectFaxServerW
0x1800050a5  test    eax, eax
0x1800050a7  jz      loc_18000512D
0x1800050ad  mov     rcx, [rbp+FaxHandle]
0x1800050b1  lea     r8, [rbp+arg_18]
0x1800050b5  lea     rdx, [rbp+Buffer]
0x1800050b9  call    cs:__imp_FaxEnumPortsExW
0x1800050bf  test    eax, eax
0x1800050c1  jz      short loc_180005118
0x1800050c3  mov     edx, [rbp+arg_18]
0x1800050c6  test    edx, edx
0x1800050c8  jz      short loc_18000512D
0x1800050ca  mov     rdi, [rbp+Buffer]
0x1800050ce  xor     r8d, r8d
0x1800050d1  test    edx, edx
0x1800050d3  jz      short loc_1800050F4
0x1800050d5  lea     rcx, [r8+r8*8]
0x1800050d9  lea     rax, [rdi+rcx*8]
0x1800050dd  cmp     [rax+28h], ebx
0x1800050e0  jnz     short loc_1800050F1
0x1800050e2  cmp     [rax+2Ch], ebx
0x1800050e5  jnz     short loc_1800050F1
0x1800050e7  inc     r8d
0x1800050ea  cmp     r8d, edx
0x1800050ed  jb      short loc_1800050D5
0x1800050ef  jmp     short loc_1800050F4
0x1800050f1  mov     rdi, rax
0x1800050f4  mov     rcx, rsi; lpMachineName
0x1800050f7  call    SetServiceStartupType
0x1800050fc  test    eax, eax
0x1800050fe  jnz     short loc_180005118
0x180005100  mov     edx, [rdi+4]
0x180005103  mov     r8, rdi
0x180005106  mov     [rdi+2Ch], r14d
0x18000510a  mov     rcx, [rbp+FaxHandle]
0x18000510e  call    cs:__imp_FaxSetPortExW
0x180005114  test    eax, eax
0x180005116  jnz     short loc_18000512D
0x180005118  call    cs:__imp_GetLastError
0x18000511e  mov     ebx, eax
0x180005120  test    eax, eax
0x180005122  jle     short loc_18000512D
0x180005124  movzx   ebx, ax
0x180005127  or      ebx, 80070000h
0x18000512d  mov     rcx, [rbp+FaxHandle]; FaxHandle
0x180005131  test    rcx, rcx
0x180005134  jz      short loc_18000513C
0x180005136  call    cs:__imp_FaxClose
0x18000513c  mov     rcx, [rbp+Buffer]; Buffer
0x180005140  test    rcx, rcx
0x180005143  jz      short loc_18000514B
0x180005145  call    cs:__imp_FaxFreeBuffer
0x18000514b  mov     rsi, [rsp+30h+arg_8]
0x180005150  mov     eax, ebx
0x180005152  mov     rbx, [rsp+30h+arg_0]
0x180005157  add     rsp, 30h
0x18000515b  pop     r14
0x18000515d  pop     rdi
0x18000515e  pop     rbp
0x18000515f  retn
```
