# QuicTimerWheelUpdate

- ea: `0x14000da60`
- end: `0x14000db62`
- name: `QuicTimerWheelUpdate`
- size: `258`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000d7a0`
- `0x14000f400`
- `0x14000f9c0`
- `0x140022644`

## callees

- `0x14000da60`
- `0x14003c8e0`
- `0x14003ead8`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14000daf0`
- `ntoskrnl!_snprintf_s` at `0x14000db2c`
- `ntoskrnl!_snprintf_s` at `0x14000daf0`
- `ntoskrnl!_snprintf_s` at `0x14000db2c`

## pseudocode

```c
NTSTATUS __fastcall QuicTimerWheelUpdate(const void **a1)
{
  unsigned int v1; // edx
  _QWORD *v2; // rax
  __int64 v3; // r9
  _QWORD *v4; // rdx
  const void *v5; // r8
  _QWORD *v6; // rdx
  NTSTATUS result; // eax
  __int64 v8; // rcx
  char DstBuf[128]; // [rsp+40h] [rbp-98h] BYREF

  v1 = *((_DWORD *)a1 + 6);
  *a1 = (const void *)-1LL;
  a1[2] = 0;
  if ( v1 )
  {
    v2 = a1[4];
    v3 = v1;
    do
    {
      v4 = (_QWORD *)*v2;
      if ( (_QWORD *)*v2 != v2 )
      {
        v5 = (const void *)v4[165];
        v6 = v4 - 6;
        if ( v5 < *a1 )
        {
          *a1 = v5;
          a1[2] = v6;
        }
      }
      v2 += 2;
      --v3;
    }
    while ( v3 );
  }
  result = (unsigned __int8)byte_14005C48E;
  if ( a1[2] )
  {
    if ( byte_14005C48E >= 0 )
      return result;
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[time][%p] Next Expiration = {%llu, %p}.", a1, *a1, a1[2]);
  }
  else
  {
    if ( byte_14005C48E >= 0 )
      return result;
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[time][%p] Next Expiration = {NULL}.", a1);
  }
  return McTemplateU0s_EtwWriteTransfer(v8, (const EVENT_DESCRIPTOR *)QuicLogVerbose, DstBuf);
}

```

## disassembly

```asm
0x14000da60  sub     rsp, 0D8h
0x14000da67  mov     rax, cs:__security_cookie
0x14000da6e  xor     rax, rsp
0x14000da71  mov     [rsp+0D8h+var_18], rax
0x14000da79  mov     edx, [rcx+18h]
0x14000da7c  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x14000da83  mov     qword ptr [rcx+10h], 0
0x14000da8b  test    edx, edx
0x14000da8d  jz      short loc_14000DABF
0x14000da8f  mov     rax, [rcx+20h]
0x14000da93  mov     r9d, edx
0x14000da96  mov     rdx, [rax]
0x14000da99  cmp     rdx, rax
0x14000da9c  jz      short loc_14000DAB5
0x14000da9e  mov     r8, [rdx+528h]
0x14000daa5  add     rdx, 0FFFFFFFFFFFFFFD0h
0x14000daa9  cmp     r8, [rcx]
0x14000daac  jnb     short loc_14000DAB5
0x14000daae  mov     [rcx], r8
0x14000dab1  mov     [rcx+10h], rdx
0x14000dab5  add     rax, 10h
0x14000dab9  sub     r9, 1
0x14000dabd  jnz     short loc_14000DA96
0x14000dabf  mov     rdx, [rcx+10h]
0x14000dac3  movzx   eax, cs:byte_14005C48E
0x14000daca  test    rdx, rdx
0x14000dacd  jnz     short loc_14000DAFE
0x14000dacf  test    al, al
0x14000dad1  jns     short loc_14000DB49
0x14000dad3  mov     [rsp+0D8h+var_B8], rcx
0x14000dad8  lea     r9, aTimePNextExpir; "[time][%p] Next Expiration = {NULL}."
0x14000dadf  lea     rcx, [rsp+0D8h+DstBuf]; DstBuf
0x14000dae4  mov     edx, 80h; SizeInBytes
0x14000dae9  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000daf0  call    cs:__imp__snprintf_s
0x14000daf7  nop     dword ptr [rax+rax+00h]
0x14000dafc  jmp     short loc_14000DB38
0x14000dafe  test    al, al
0x14000db00  jns     short loc_14000DB49
0x14000db02  mov     rax, [rcx]
0x14000db05  lea     r9, aTimePNextExpir_0; "[time][%p] Next Expiration = {%llu, %p}"...
0x14000db0c  mov     [rsp+0D8h+var_A8], rdx
0x14000db11  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000db18  mov     [rsp+0D8h+var_B0], rax
0x14000db1d  mov     edx, 80h; SizeInBytes
0x14000db22  mov     [rsp+0D8h+var_B8], rcx
0x14000db27  lea     rcx, [rsp+0D8h+DstBuf]; DstBuf
0x14000db2c  call    cs:__imp__snprintf_s
0x14000db33  nop     dword ptr [rax+rax+00h]
0x14000db38  lea     r8, [rsp+0D8h+DstBuf]
0x14000db3d  lea     rdx, QuicLogVerbose
0x14000db44  call    McTemplateU0s_EtwWriteTransfer
0x14000db49  mov     rcx, [rsp+0D8h+var_18]
0x14000db51  xor     rcx, rsp; StackCookie
0x14000db54  call    __security_check_cookie
0x14000db59  add     rsp, 0D8h
0x14000db60  retn
```
