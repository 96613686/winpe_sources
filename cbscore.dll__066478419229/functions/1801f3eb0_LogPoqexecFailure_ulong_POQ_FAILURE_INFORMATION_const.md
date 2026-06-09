# LogPoqexecFailure(ulong,_POQ_FAILURE_INFORMATION const &)

- ea: `0x1801f3eb0`
- end: `0x1801f4189`
- name: `?LogPoqexecFailure@@YAXKAEBU_POQ_FAILURE_INFORMATION@@@Z`
- size: `729`
- prototype: `void __fastcall(unsigned int, const struct _POQ_FAILURE_INFORMATION *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1801f5628`

## callees

- `0x180019bdc`
- `0x1800eb920`
- `0x1800ec180`
- `0x1801f3eb0`
- `0x1801fbcb0`

## import_xrefs

- `ntdll!NtWriteFile` at `0x1801f40b8`
- `ntdll!NtWriteFile` at `0x1801f4102`
- `ntdll!NtWriteFile` at `0x1801f414e`
- `ntdll!NtWriteFile` at `0x1801f40b8`
- `ntdll!NtWriteFile` at `0x1801f4102`
- `ntdll!NtWriteFile` at `0x1801f414e`

## string_xrefs

- `0x1801f3f8e`: `CopyFile`
- `0x1801f3f64`: `CreateFile`
- `0x1801f3f70`: `HardLinkFile`
- `0x1801f3f7c`: `DeleteFile`
- `0x1801f3f85`: `MoveFile`
- `0x1801f3f97`: `DeleteKey`
- `0x1801f3f40`: `CreateKey`
- `0x1801f3f4c`: `SetFileInformation`
- `0x1801f3f58`: `CreateDirectory`
- `0x1801f3fe7`: `SetKeySecurity`
- `0x1801f3ff0`: `DeleteKeyValue`
- `0x1801f3fcc`: `DecompressFile`

## pseudocode

```c
void __fastcall LogPoqexecFailure(__int64 a1, const struct _POQ_FAILURE_INFORMATION *a2)
{
  const char *v3; // rcx
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  ULONG Length; // edi
  __int64 v19; // rcx
  union _LARGE_INTEGER ByteOffset; // [rsp+50h] [rbp-B0h] BYREF
  ULONG v21[4]; // [rsp+58h] [rbp-A8h] BYREF
  PVOID v22; // [rsp+68h] [rbp-98h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-90h] BYREF
  char Buffer[1024]; // [rsp+80h] [rbp-80h] BYREF

  if ( g_hFailureLogFile )
  {
    v3 = (const char *)&dword_1802ECF3C;
    v22 = 0;
    v4 = *((_DWORD *)a2 + 1);
    *(_OWORD *)v21 = 0;
    if ( v4 > 0xA )
    {
      v12 = v4 - 11;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( v14 )
          {
            v15 = v14 - 1;
            if ( v15 )
            {
              v16 = v15 - 1;
              if ( v16 )
              {
                v17 = v16 - 2;
                if ( v17 )
                {
                  if ( v17 == 2 )
                    v3 = "SetKeyInfos";
                }
                else
                {
                  v3 = "DecompressFile";
                }
              }
              else
              {
                v3 = "FlushFileBuffers";
              }
            }
            else
            {
              v3 = "BeginTransaction";
            }
          }
          else
          {
            v3 = "SetKeySecurity";
          }
        }
        else
        {
          v3 = "DeleteKeyValue";
        }
      }
      else
      {
        v3 = "SetKeyValue";
      }
    }
    else if ( v4 == 10 )
    {
      v3 = "DeleteKey";
    }
    else
    {
      v5 = v4 - 1;
      if ( v5 )
      {
        v6 = v5 - 1;
        if ( v6 )
        {
          v7 = v6 - 1;
          if ( v7 )
          {
            v8 = v7 - 1;
            if ( v8 )
            {
              v9 = v8 - 2;
              if ( v9 )
              {
                v10 = v9 - 1;
                if ( v10 )
                {
                  v11 = v10 - 1;
                  if ( v11 )
                  {
                    if ( v11 == 1 )
                      v3 = "CreateKey";
                  }
                  else
                  {
                    v3 = "SetFileInformation";
                  }
                }
                else
                {
                  v3 = "CreateDirectory";
                }
              }
              else
              {
                v3 = "CreateFile";
              }
            }
            else
            {
              v3 = "HardLinkFile";
            }
          }
          else
          {
            v3 = "DeleteFile";
          }
        }
        else
        {
          v3 = "MoveFile";
        }
      }
      else
      {
        v3 = "CopyFile";
      }
    }
    Length = sprintf_s(
               Buffer,
               0x400u,
               "%llx: %lx, %lx, %Ix, %lx, %s ;",
               g_PoqExecStartTime.QuadPart,
               2098,
               *(_DWORD *)a2,
               *((_QWORD *)a2 + 2),
               *((_DWORD *)a2 + 2),
               v3);
    RtlDuplicateLUnicodeStringToLUtf8String((char *)a2 + 24, v21);
    v19 = *(_QWORD *)v21;
    ByteOffset.QuadPart = -1;
    if ( *(_QWORD *)v21 > 0xFFFFFFFF )
      v19 = 0xFFFFFFFFLL;
    *(_QWORD *)v21 = v19;
    IoStatusBlock = 0;
    if ( Length != -1 )
    {
      NtWriteFile(g_hFailureLogFile, 0, 0, 0, &IoStatusBlock, Buffer, Length, &ByteOffset, 0);
      NtWriteFile(g_hFailureLogFile, 0, 0, 0, &IoStatusBlock, v22, v21[0], &ByteOffset, 0);
      NtWriteFile(g_hFailureLogFile, 0, 0, 0, &IoStatusBlock, "\r\n", 2u, &ByteOffset, 0);
    }
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v21);
  }
}

```

## disassembly

```asm
0x1801f3eb0  mov     [rsp-8+arg_0], rbx
0x1801f3eb5  mov     [rsp-8+arg_10], rdi
0x1801f3eba  push    rbp
0x1801f3ebb  lea     rbp, [rsp-390h]
0x1801f3ec3  sub     rsp, 490h
0x1801f3eca  mov     rax, cs:__security_cookie
0x1801f3ed1  xor     rax, rsp
0x1801f3ed4  mov     [rbp+390h+var_10], rax
0x1801f3edb  cmp     cs:?g_hFailureLogFile@@3PEAXEA, 0; void * g_hFailureLogFile
0x1801f3ee3  mov     rbx, rdx
0x1801f3ee6  jz      loc_1801F4164
0x1801f3eec  xor     eax, eax
0x1801f3eee  lea     rcx, dword_1802ECF3C
0x1801f3ef5  mov     [rsp+490h+var_428], rax
0x1801f3efa  xorps   xmm0, xmm0
0x1801f3efd  mov     eax, [rdx+4]
0x1801f3f00  movups  xmmword ptr [rsp+490h+var_438], xmm0
0x1801f3f05  cmp     eax, 0Ah
0x1801f3f08  ja      loc_1801F3FA0
0x1801f3f0e  jz      loc_1801F3F97
0x1801f3f14  sub     eax, 1
0x1801f3f17  jz      short loc_1801F3F8E
0x1801f3f19  sub     eax, 1
0x1801f3f1c  jz      short loc_1801F3F85
0x1801f3f1e  sub     eax, 1
0x1801f3f21  jz      short loc_1801F3F7C
0x1801f3f23  sub     eax, 1
0x1801f3f26  jz      short loc_1801F3F70
0x1801f3f28  sub     eax, 2
0x1801f3f2b  jz      short loc_1801F3F64
0x1801f3f2d  sub     eax, 1
0x1801f3f30  jz      short loc_1801F3F58
0x1801f3f32  sub     eax, 1
0x1801f3f35  jz      short loc_1801F3F4C
0x1801f3f37  cmp     eax, 1
0x1801f3f3a  jnz     loc_1801F4000
0x1801f3f40  lea     rcx, aCreatekey; "CreateKey"
0x1801f3f47  jmp     loc_1801F4000
0x1801f3f4c  lea     rcx, aSetfileinforma_0; "SetFileInformation"
0x1801f3f53  jmp     loc_1801F4000
0x1801f3f58  lea     rcx, aCreatedirector; "CreateDirectory"
0x1801f3f5f  jmp     loc_1801F4000
0x1801f3f64  lea     rcx, aCreatefile_0; "CreateFile"
0x1801f3f6b  jmp     loc_1801F4000
0x1801f3f70  lea     rcx, aHardlinkfile; "HardLinkFile"
0x1801f3f77  jmp     loc_1801F4000
0x1801f3f7c  lea     rcx, aDeletefile; "DeleteFile"
0x1801f3f83  jmp     short loc_1801F4000
0x1801f3f85  lea     rcx, aMovefile; "MoveFile"
0x1801f3f8c  jmp     short loc_1801F4000
0x1801f3f8e  lea     rcx, aCopyfile; "CopyFile"
0x1801f3f95  jmp     short loc_1801F4000
0x1801f3f97  lea     rcx, aDeletekey; "DeleteKey"
0x1801f3f9e  jmp     short loc_1801F4000
0x1801f3fa0  sub     eax, 0Bh
0x1801f3fa3  jz      short loc_1801F3FF9
0x1801f3fa5  sub     eax, 1
0x1801f3fa8  jz      short loc_1801F3FF0
0x1801f3faa  sub     eax, 1
0x1801f3fad  jz      short loc_1801F3FE7
0x1801f3faf  sub     eax, 1
0x1801f3fb2  jz      short loc_1801F3FDE
0x1801f3fb4  sub     eax, 1
0x1801f3fb7  jz      short loc_1801F3FD5
0x1801f3fb9  sub     eax, 2
0x1801f3fbc  jz      short loc_1801F3FCC
0x1801f3fbe  cmp     eax, 2
0x1801f3fc1  jnz     short loc_1801F4000
0x1801f3fc3  lea     rcx, aSetkeyinfos; "SetKeyInfos"
0x1801f3fca  jmp     short loc_1801F4000
0x1801f3fcc  lea     rcx, aDecompressfile; "DecompressFile"
0x1801f3fd3  jmp     short loc_1801F4000
0x1801f3fd5  lea     rcx, aFlushfilebuffe; "FlushFileBuffers"
0x1801f3fdc  jmp     short loc_1801F4000
0x1801f3fde  lea     rcx, aBegintransacti; "BeginTransaction"
0x1801f3fe5  jmp     short loc_1801F4000
0x1801f3fe7  lea     rcx, aSetkeysecurity; "SetKeySecurity"
0x1801f3fee  jmp     short loc_1801F4000
0x1801f3ff0  lea     rcx, aDeletekeyvalue; "DeleteKeyValue"
0x1801f3ff7  jmp     short loc_1801F4000
0x1801f3ff9  lea     rcx, aSetkeyvalue; "SetKeyValue"
0x1801f4000  mov     eax, [rdx+8]
0x1801f4003  lea     r8, aLlxLxLxIxLxS; "%llx: %lx, %lx, %Ix, %lx, %s ;"
0x1801f400a  mov     r9, qword ptr cs:?g_PoqExecStartTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_PoqExecStartTime ...
0x1801f4011  mov     [rsp+490h+Key], rcx
0x1801f4016  lea     rcx, [rbp+390h+Buffer]; Buffer
0x1801f401a  mov     dword ptr [rsp+490h+ByteOffset], eax
0x1801f401e  mov     rax, [rdx+10h]
0x1801f4022  mov     qword ptr [rsp+490h+Length], rax
0x1801f4027  mov     eax, [rdx]
0x1801f4029  mov     edx, 400h; BufferCount
0x1801f402e  mov     dword ptr [rsp+490h+var_468], eax
0x1801f4032  mov     dword ptr [rsp+490h+IoStatusBlock], 832h
0x1801f403a  call    sprintf_s
0x1801f403f  lea     rcx, [rbx+18h]
0x1801f4043  mov     edi, eax
0x1801f4045  lea     rdx, [rsp+490h+var_438]
0x1801f404a  call    RtlDuplicateLUnicodeStringToLUtf8String
0x1801f404f  mov     rcx, qword ptr [rsp+490h+var_438]
0x1801f4054  mov     eax, 0FFFFFFFFh
0x1801f4059  cmp     rcx, rax
0x1801f405c  mov     qword ptr [rsp+490h+var_440], 0FFFFFFFFFFFFFFFFh
0x1801f4065  xorps   xmm0, xmm0
0x1801f4068  cmova   rcx, rax
0x1801f406c  mov     qword ptr [rsp+490h+var_438], rcx
0x1801f4071  movups  xmmword ptr [rsp+490h+var_420], xmm0
0x1801f4076  cmp     edi, 0FFFFFFFFh
0x1801f4079  jz      loc_1801F415A
0x1801f407f  mov     rcx, cs:?g_hFailureLogFile@@3PEAXEA; FileHandle
0x1801f4086  lea     rax, [rsp+490h+var_440]
0x1801f408b  mov     [rsp+490h+Key], 0; Key
0x1801f4094  xor     r9d, r9d; ApcContext
0x1801f4097  mov     [rsp+490h+ByteOffset], rax; ByteOffset
0x1801f409c  xor     r8d, r8d; ApcRoutine
0x1801f409f  lea     rax, [rbp+390h+Buffer]
0x1801f40a3  mov     [rsp+490h+Length], edi; Length
0x1801f40a7  mov     [rsp+490h+var_468], rax; Buffer
0x1801f40ac  xor     edx, edx; Event
0x1801f40ae  lea     rax, [rsp+490h+var_420]
0x1801f40b3  mov     [rsp+490h+IoStatusBlock], rax; IoStatusBlock
0x1801f40b8  call    cs:__imp_NtWriteFile
0x1801f40bf  nop     dword ptr [rax+rax+00h]
0x1801f40c4  mov     rcx, cs:?g_hFailureLogFile@@3PEAXEA; FileHandle
0x1801f40cb  lea     rax, [rsp+490h+var_440]
0x1801f40d0  mov     [rsp+490h+Key], 0; Key
0x1801f40d9  xor     r9d, r9d; ApcContext
0x1801f40dc  mov     [rsp+490h+ByteOffset], rax; ByteOffset
0x1801f40e1  xor     r8d, r8d; ApcRoutine
0x1801f40e4  mov     eax, [rsp+490h+var_438]
0x1801f40e8  xor     edx, edx; Event
0x1801f40ea  mov     [rsp+490h+Length], eax; Length
0x1801f40ee  mov     rax, [rsp+490h+var_428]
0x1801f40f3  mov     [rsp+490h+var_468], rax; Buffer
0x1801f40f8  lea     rax, [rsp+490h+var_420]
0x1801f40fd  mov     [rsp+490h+IoStatusBlock], rax; IoStatusBlock
0x1801f4102  call    cs:__imp_NtWriteFile
0x1801f4109  nop     dword ptr [rax+rax+00h]
0x1801f410e  mov     rcx, cs:?g_hFailureLogFile@@3PEAXEA; FileHandle
0x1801f4115  lea     rax, [rsp+490h+var_440]
0x1801f411a  mov     [rsp+490h+Key], 0; Key
0x1801f4123  xor     r9d, r9d; ApcContext
0x1801f4126  mov     [rsp+490h+ByteOffset], rax; ByteOffset
0x1801f412b  xor     r8d, r8d; ApcRoutine
0x1801f412e  lea     rax, asc_18035E33C; "\r\n"
0x1801f4135  mov     [rsp+490h+Length], 2; Length
0x1801f413d  mov     [rsp+490h+var_468], rax; Buffer
0x1801f4142  xor     edx, edx; Event
0x1801f4144  lea     rax, [rsp+490h+var_420]
0x1801f4149  mov     [rsp+490h+IoStatusBlock], rax; IoStatusBlock
0x1801f414e  call    cs:__imp_NtWriteFile
0x1801f4155  nop     dword ptr [rax+rax+00h]
0x1801f415a  lea     rcx, [rsp+490h+var_438]
0x1801f415f  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1801f4164  mov     rcx, [rbp+390h+var_10]
0x1801f416b  xor     rcx, rsp; StackCookie
0x1801f416e  call    __security_check_cookie
0x1801f4173  lea     r11, [rsp+490h+var_s0]
0x1801f417b  mov     rbx, [r11+10h]
0x1801f417f  mov     rdi, [r11+20h]
0x1801f4183  mov     rsp, r11
0x1801f4186  pop     rbp
0x1801f4187  retn
```
