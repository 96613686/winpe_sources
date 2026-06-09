# mapFCIError

- ea: `0x140006e0c`
- end: `0x140007054`
- name: `mapFCIError`
- size: `584`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000488c`
- `0x140004f94`
- `0x1400052b0`
- `0x140005410`
- `0x140007e18`

## callees

- `0x140006e0c`
- `0x140008620`

## string_xrefs

- `0x140006fcc`: `(%1)Unknown compression type`
- `0x140007019`: `(%1)Failure compressing data from file %2`
- `0x140006fa3`: `(%1)Failure opening source file %2: %3`
- `0x140006f9a`: `(%1)Failure reading source file %2: %3`
- `0x140006f73`: `(%1)Failure on temporary file: %2`
- `0x140006e86`: `create process failed`
- `0x140006e9e`: `bad file handle/incompatible I/O operation`
- `0x140006ecb`: `file already exists`
- `0x140006ec2`: `file/path does not exist`
- `0x140006f3d`: `cannot move file across devices`

## pseudocode

```c
__int64 __fastcall mapFCIError(__int64 a1, __int64 a2, const char *a3, _DWORD *a4)
{
  int v8; // r10d
  int v9; // r10d
  int v10; // r10d
  int v11; // r10d
  int v12; // r10d
  int v13; // r10d
  int v14; // r10d
  int v15; // r10d
  const char *v16; // rcx
  int v17; // r10d
  int v18; // r10d
  int v19; // r10d
  int v20; // r10d
  int v21; // r10d
  int v22; // r10d
  int v23; // r8d
  const char *v24; // rdx
  const char *v25; // rdx
  __int64 result; // rax
  const char *v27; // rdx
  const char *v28; // [rsp+20h] [rbp-18h]

  v8 = a4[1];
  if ( v8 <= 17 )
  {
    if ( v8 == 17 )
    {
      v16 = "file already exists";
      goto LABEL_35;
    }
    v9 = v8 - 2;
    if ( !v9 )
    {
      v16 = "file/path does not exist";
      goto LABEL_35;
    }
    v10 = v9 - 5;
    if ( !v10 )
    {
      v16 = "arg list too long/out of environment space";
      goto LABEL_35;
    }
    v11 = v10 - 1;
    if ( !v11 )
    {
      v16 = "invalid executable format";
      goto LABEL_35;
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
      v16 = "bad file handle/incompatible I/O operation";
      goto LABEL_35;
    }
    v13 = v12 - 1;
    if ( !v13 )
    {
      v16 = "no child processes";
      goto LABEL_35;
    }
    v14 = v13 - 1;
    if ( !v14 )
    {
      v16 = "create process failed";
      goto LABEL_35;
    }
    v15 = v14 - 1;
    if ( !v15 )
    {
      v16 = "out of memory";
      goto LABEL_35;
    }
    if ( v15 == 1 )
    {
      v16 = "permission denied";
      goto LABEL_35;
    }
    goto LABEL_27;
  }
  v17 = v8 - 18;
  if ( v17 )
  {
    v18 = v17 - 4;
    if ( v18 )
    {
      v19 = v18 - 2;
      if ( v19 )
      {
        v20 = v19 - 4;
        if ( v20 )
        {
          v21 = v20 - 5;
          if ( v21 )
          {
            v22 = v21 - 1;
            if ( v22 )
            {
              if ( v22 != 2 )
              {
LABEL_27:
                v16 = "<unknown C run-time error>";
                goto LABEL_35;
              }
              v16 = "deadlock would occur?";
            }
            else
            {
              v16 = "math argument out of range";
            }
          }
          else
          {
            v16 = "bad argument to math function";
          }
        }
        else
        {
          v16 = "out of disk space";
        }
      }
      else
      {
        v16 = "out of file handles";
      }
    }
    else
    {
      v16 = "invalid argument";
    }
  }
  else
  {
    v16 = "cannot move file across devices";
  }
LABEL_35:
  v23 = *a4;
  if ( (int)*a4 <= 5 )
  {
    switch ( v23 )
    {
      case 5:
        v25 = "(%1)Unknown compression type";
        return ErrSet(a1, v25, "%s", a3);
      case 0:
        return result;
      case 1:
        v27 = "(%1)Failure opening source file %2: %3";
        break;
      case 2:
        v27 = "(%1)Failure reading source file %2: %3";
        break;
      case 3:
        v25 = "(%1)Out of memory";
        return ErrSet(a1, v25, "%s", a3);
      case 4:
        v24 = "(%1)Failure on temporary file: %2";
LABEL_58:
        v28 = v16;
        return ErrSet(a1, v24, "%s%s", a3, v28);
      default:
        return ErrSet(a1, "(%1)Unknown error(%2)", "%s%d", a3, *a4);
    }
    return ErrSet(a1, v27, "%s%s%s", a3, (const char *)(a2 + 228), v16);
  }
  if ( v23 == 6 )
  {
    v24 = "(%1)Failure creating or writing cabinet file: %2";
    goto LABEL_58;
  }
  if ( v23 == 7 )
  {
    v25 = "(%1)User aborted";
    return ErrSet(a1, v25, "%s", a3);
  }
  if ( v23 != 8 )
  {
    if ( v23 != 9 )
      return ErrSet(a1, "(%1)Unknown error(%2)", "%s%d", a3, *a4);
    v25 = "(%1)Data-size or file-count exceeded CAB format limits";
    return ErrSet(a1, v25, "%s", a3);
  }
  v28 = (const char *)(a2 + 228);
  v24 = "(%1)Failure compressing data from file %2";
  return ErrSet(a1, v24, "%s%s", a3, v28);
}

```

## disassembly

```asm
0x140006e0c  mov     [rsp+arg_0], rbx
0x140006e11  push    rdi
0x140006e12  sub     rsp, 30h
0x140006e16  mov     rbx, r9
0x140006e19  mov     rdi, rdx
0x140006e1c  mov     r9, r8
0x140006e1f  mov     r11, rcx
0x140006e22  mov     r10d, [rbx+4]
0x140006e26  cmp     r10d, 11h
0x140006e2a  jg      loc_140006ED4
0x140006e30  jz      loc_140006ECB
0x140006e36  sub     r10d, 2
0x140006e3a  jz      loc_140006EC2
0x140006e40  sub     r10d, 5
0x140006e44  jz      short loc_140006EB6
0x140006e46  sub     r10d, 1
0x140006e4a  jz      short loc_140006EAA
0x140006e4c  sub     r10d, 1
0x140006e50  jz      short loc_140006E9E
0x140006e52  sub     r10d, 1
0x140006e56  jz      short loc_140006E92
0x140006e58  sub     r10d, 1
0x140006e5c  jz      short loc_140006E86
0x140006e5e  sub     r10d, 1
0x140006e62  jz      short loc_140006E7A
0x140006e64  cmp     r10d, 1
0x140006e68  jnz     loc_140006EFE
0x140006e6e  lea     rcx, aPermissionDeni; "permission denied"
0x140006e75  jmp     loc_140006F44
0x140006e7a  lea     rcx, aOutOfMemory; "out of memory"
0x140006e81  jmp     loc_140006F44
0x140006e86  lea     rcx, aCreateProcessF; "create process failed"
0x140006e8d  jmp     loc_140006F44
0x140006e92  lea     rcx, aNoChildProcess; "no child processes"
0x140006e99  jmp     loc_140006F44
0x140006e9e  lea     rcx, aBadFileHandleI; "bad file handle/incompatible I/O operat"...
0x140006ea5  jmp     loc_140006F44
0x140006eaa  lea     rcx, aInvalidExecuta; "invalid executable format"
0x140006eb1  jmp     loc_140006F44
0x140006eb6  lea     rcx, aArgListTooLong; "arg list too long/out of environment sp"...
0x140006ebd  jmp     loc_140006F44
0x140006ec2  lea     rcx, aFilePathDoesNo; "file/path does not exist"
0x140006ec9  jmp     short loc_140006F44
0x140006ecb  lea     rcx, aFileAlreadyExi; "file already exists"
0x140006ed2  jmp     short loc_140006F44
0x140006ed4  sub     r10d, 12h
0x140006ed8  jz      short loc_140006F3D
0x140006eda  sub     r10d, 4
0x140006ede  jz      short loc_140006F34
0x140006ee0  sub     r10d, 2
0x140006ee4  jz      short loc_140006F2B
0x140006ee6  sub     r10d, 4
0x140006eea  jz      short loc_140006F22
0x140006eec  sub     r10d, 5
0x140006ef0  jz      short loc_140006F19
0x140006ef2  sub     r10d, 1
0x140006ef6  jz      short loc_140006F10
0x140006ef8  cmp     r10d, 2
0x140006efc  jz      short loc_140006F07
0x140006efe  lea     rcx, aUnknownCRunTim; "<unknown C run-time error>"
0x140006f05  jmp     short loc_140006F44
0x140006f07  lea     rcx, aDeadlockWouldO; "deadlock would occur?"
0x140006f0e  jmp     short loc_140006F44
0x140006f10  lea     rcx, aMathArgumentOu; "math argument out of range"
0x140006f17  jmp     short loc_140006F44
0x140006f19  lea     rcx, aBadArgumentToM; "bad argument to math function"
0x140006f20  jmp     short loc_140006F44
0x140006f22  lea     rcx, aOutOfDiskSpace; "out of disk space"
0x140006f29  jmp     short loc_140006F44
0x140006f2b  lea     rcx, aOutOfFileHandl; "out of file handles"
0x140006f32  jmp     short loc_140006F44
0x140006f34  lea     rcx, aInvalidArgumen; "invalid argument"
0x140006f3b  jmp     short loc_140006F44
0x140006f3d  lea     rcx, aCannotMoveFile; "cannot move file across devices"
0x140006f44  mov     r8d, [rbx]
0x140006f47  cmp     r8d, 5
0x140006f4b  jg      loc_140006FD5
0x140006f51  jz      short loc_140006FCC
0x140006f53  mov     edx, r8d
0x140006f56  test    r8d, r8d
0x140006f59  jz      loc_140007049
0x140006f5f  sub     edx, 1
0x140006f62  jz      short loc_140006FA3
0x140006f64  sub     edx, 1
0x140006f67  jz      short loc_140006F9A
0x140006f69  sub     edx, 1
0x140006f6c  jz      short loc_140006F7F
0x140006f6e  cmp     edx, 1
0x140006f71  jnz     short loc_140006FEC
0x140006f73  lea     rdx, a1FailureOnTemp; "(%1)Failure on temporary file: %2"
0x140006f7a  jmp     loc_140007035
0x140006f7f  lea     rdx, a1OutOfMemory; "(%1)Out of memory"
0x140006f86  lea     r8, aS_4; "%s"
0x140006f8d  mov     rcx, r11
0x140006f90  call    ErrSet
0x140006f95  jmp     loc_140007049
0x140006f9a  lea     rdx, a1FailureReadin; "(%1)Failure reading source file %2: %3"
0x140006fa1  jmp     short loc_140006FAA
0x140006fa3  lea     rdx, a1FailureOpenin; "(%1)Failure opening source file %2: %3"
0x140006faa  mov     [rsp+38h+var_10], rcx
0x140006faf  lea     rax, [rdi+0E4h]
0x140006fb6  mov     rcx, r11
0x140006fb9  mov     [rsp+38h+var_18], rax
0x140006fbe  lea     r8, aSSS; "%s%s%s"
0x140006fc5  call    ErrSet
0x140006fca  jmp     short loc_140007049
0x140006fcc  lea     rdx, a1UnknownCompre; "(%1)Unknown compression type"
0x140006fd3  jmp     short loc_140006F86
0x140006fd5  mov     edx, r8d
0x140006fd8  sub     edx, 6
0x140006fdb  jz      short loc_14000702E
0x140006fdd  sub     edx, 1
0x140006fe0  jz      short loc_140007022
0x140006fe2  sub     edx, 1
0x140006fe5  jz      short loc_14000700D
0x140006fe7  cmp     edx, 1
0x140006fea  jz      short loc_140007001
0x140006fec  mov     dword ptr [rsp+38h+var_18], r8d
0x140006ff1  lea     rdx, a1UnknownError2; "(%1)Unknown error(%2)"
0x140006ff8  lea     r8, aSD; "%s%d"
0x140006fff  jmp     short loc_140007041
0x140007001  lea     rdx, a1DataSizeOrFil; "(%1)Data-size or file-count exceeded CA"...
0x140007008  jmp     loc_140006F86
0x14000700d  lea     rax, [rdi+0E4h]
0x140007014  mov     [rsp+38h+var_18], rax
0x140007019  lea     rdx, a1FailureCompre; "(%1)Failure compressing data from file "...
0x140007020  jmp     short loc_14000703A
0x140007022  lea     rdx, a1UserAborted; "(%1)User aborted"
0x140007029  jmp     loc_140006F86
0x14000702e  lea     rdx, a1FailureCreati; "(%1)Failure creating or writing cabinet"...
0x140007035  mov     [rsp+38h+var_18], rcx
0x14000703a  lea     r8, aSS_1; "%s%s"
0x140007041  mov     rcx, r11
0x140007044  call    ErrSet
0x140007049  mov     rbx, [rsp+38h+arg_0]
0x14000704e  add     rsp, 30h
0x140007052  pop     rdi
0x140007053  retn
```
