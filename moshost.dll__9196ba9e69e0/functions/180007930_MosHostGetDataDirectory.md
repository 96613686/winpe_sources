# MosHostGetDataDirectory

- ea: `0x180007930`
- end: `0x1800079d1`
- name: `MosHostGetDataDirectory`
- size: `161`
- prototype: `int __fastcall(__int64, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001d00`
- `0x180007298`
- `0x180007930`

## import_xrefs

- `MosStorage!MosStorageGetDataDirectory` at `0x180007996`
- `MosStorage!MosStorageGetDataDirectory` at `0x180007996`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180007989`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180007989`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800079af`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800079af`

## string_xrefs

- `0x180007982`: `MosHostGetDataDirectory`
- `0x1800079a6`: `MosHostGetDataDirectory`

## pseudocode

```c
int __fastcall MosHostGetDataDirectory(__int64 a1, unsigned __int16 *a2, unsigned int a3)
{
  int DataDirectory; // eax

  if ( (Microsoft_Windows_MosHostEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, GetDataDirectory);
  if ( !a2 )
    return ZTraceReportOriginationNoThis(-2147467261, "MosHostGetDataDirectory", 30);
  DataDirectory = MosStorageGetDataDirectory(a2, a3);
  if ( DataDirectory >= 0 )
    return 0;
  else
    return ZTraceReportPropagationNoThis(DataDirectory, "MosHostGetDataDirectory", 32);
}

```

## disassembly

```asm
0x180007930  mov     [rsp+arg_0], rbx
0x180007935  push    rdi
0x180007936  sub     rsp, 50h
0x18000793a  mov     rax, cs:__security_cookie
0x180007941  xor     rax, rsp
0x180007944  mov     [rsp+58h+var_18], rax
0x180007949  mov     r9d, 1
0x18000794f  mov     edi, r8d
0x180007952  test    cs:Microsoft_Windows_MosHostEnableBits, r9b
0x180007959  mov     rbx, rdx
0x18000795c  jz      short loc_180007974
0x18000795e  lea     rax, [rsp+58h+var_28]
0x180007963  lea     rdx, GetDataDirectory
0x18000796a  mov     [rsp+58h+var_38], rax
0x18000796f  call    McGenEventWrite_EventWriteTransfer
0x180007974  test    rbx, rbx
0x180007977  jnz     short loc_180007991
0x180007979  lea     r8d, [rbx+1Eh]
0x18000797d  mov     ecx, 80004003h
0x180007982  lea     rdx, aMoshostgetdata; "MosHostGetDataDirectory"
0x180007989  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000798f  jmp     short loc_1800079B9
0x180007991  mov     edx, edi
0x180007993  mov     rcx, rbx
0x180007996  call    cs:__imp_?MosStorageGetDataDirectory@@YAJPEAGK@Z; MosStorageGetDataDirectory(ushort *,ulong)
0x18000799c  test    eax, eax
0x18000799e  jns     short loc_1800079B7
0x1800079a0  mov     r8d, 20h ; ' '
0x1800079a6  lea     rdx, aMoshostgetdata; "MosHostGetDataDirectory"
0x1800079ad  mov     ecx, eax
0x1800079af  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x1800079b5  jmp     short loc_1800079B9
0x1800079b7  xor     eax, eax
0x1800079b9  mov     rcx, [rsp+58h+var_18]
0x1800079be  xor     rcx, rsp; StackCookie
0x1800079c1  call    __security_check_cookie
0x1800079c6  mov     rbx, [rsp+58h+arg_0]
0x1800079cb  add     rsp, 50h
0x1800079cf  pop     rdi
0x1800079d0  retn
```
