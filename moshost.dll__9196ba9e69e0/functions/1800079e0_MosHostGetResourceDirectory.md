# MosHostGetResourceDirectory

- ea: `0x1800079e0`
- end: `0x180007a81`
- name: `MosHostGetResourceDirectory`
- size: `161`
- prototype: `int __fastcall(__int64, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001d00`
- `0x180007298`
- `0x1800079e0`

## import_xrefs

- `MosStorage!MosStorageGetResourceDirectory` at `0x180007a46`
- `MosStorage!MosStorageGetResourceDirectory` at `0x180007a46`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180007a14`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180007a14`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007a5f`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007a5f`

## string_xrefs

- `0x180007a0d`: `MosHostGetResourceDirectory`
- `0x180007a56`: `MosHostGetResourceDirectory`

## pseudocode

```c
int __fastcall MosHostGetResourceDirectory(__int64 a1, unsigned __int16 *a2, unsigned int a3)
{
  int ResourceDirectory; // eax

  if ( !a2 )
    return ZTraceReportOriginationNoThis(-2147467261, "MosHostGetResourceDirectory", 48);
  if ( (Microsoft_Windows_MosHostEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, GetResourceDirectory);
  ResourceDirectory = MosStorageGetResourceDirectory(a2, a3);
  if ( ResourceDirectory >= 0 )
    return 0;
  else
    return ZTraceReportPropagationNoThis(ResourceDirectory, "MosHostGetResourceDirectory", 52);
}

```

## disassembly

```asm
0x1800079e0  mov     [rsp+arg_0], rbx
0x1800079e5  push    rdi
0x1800079e6  sub     rsp, 50h
0x1800079ea  mov     rax, cs:__security_cookie
0x1800079f1  xor     rax, rsp
0x1800079f4  mov     [rsp+58h+var_18], rax
0x1800079f9  mov     edi, r8d
0x1800079fc  mov     rbx, rdx
0x1800079ff  test    rdx, rdx
0x180007a02  jnz     short loc_180007A1C
0x180007a04  lea     r8d, [rdx+30h]
0x180007a08  mov     ecx, 80004003h
0x180007a0d  lea     rdx, aMoshostgetreso; "MosHostGetResourceDirectory"
0x180007a14  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180007a1a  jmp     short loc_180007A69
0x180007a1c  mov     r9d, 1
0x180007a22  test    cs:Microsoft_Windows_MosHostEnableBits, r9b
0x180007a29  jz      short loc_180007A41
0x180007a2b  lea     rax, [rsp+58h+var_28]
0x180007a30  lea     rdx, GetResourceDirectory
0x180007a37  mov     [rsp+58h+var_38], rax
0x180007a3c  call    McGenEventWrite_EventWriteTransfer
0x180007a41  mov     edx, edi
0x180007a43  mov     rcx, rbx
0x180007a46  call    cs:__imp_?MosStorageGetResourceDirectory@@YAJPEAGK@Z; MosStorageGetResourceDirectory(ushort *,ulong)
0x180007a4c  test    eax, eax
0x180007a4e  jns     short loc_180007A67
0x180007a50  mov     r8d, 34h ; '4'
0x180007a56  lea     rdx, aMoshostgetreso; "MosHostGetResourceDirectory"
0x180007a5d  mov     ecx, eax
0x180007a5f  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180007a65  jmp     short loc_180007A69
0x180007a67  xor     eax, eax
0x180007a69  mov     rcx, [rsp+58h+var_18]
0x180007a6e  xor     rcx, rsp; StackCookie
0x180007a71  call    __security_check_cookie
0x180007a76  mov     rbx, [rsp+58h+arg_0]
0x180007a7b  add     rsp, 50h
0x180007a7f  pop     rdi
0x180007a80  retn
```
