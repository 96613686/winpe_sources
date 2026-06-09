# MosHostGetBrowseCacheSizeInMBytes

- ea: `0x180007550`
- end: `0x1800075e3`
- name: `MosHostGetBrowseCacheSizeInMBytes`
- size: `147`
- prototype: `int __fastcall(__int64, unsigned int *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001d00`
- `0x180007298`
- `0x180007550`

## import_xrefs

- `MosStorage!MosStorageGetBrowseCacheSizeInMBytes` at `0x1800075ad`
- `MosStorage!MosStorageGetBrowseCacheSizeInMBytes` at `0x1800075ad`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800075a2`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800075a2`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800075c6`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800075c6`

## string_xrefs

- `0x18000759b`: `MosHostGetBrowseCacheSizeInMBytes`
- `0x1800075bd`: `MosHostGetBrowseCacheSizeInMBytes`

## pseudocode

```c
int __fastcall MosHostGetBrowseCacheSizeInMBytes(__int64 a1, unsigned int *a2, __int64 a3)
{
  int BrowseCacheSizeInMBytes; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-28h] BYREF

  if ( (Microsoft_Windows_MosHostEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)GetBrowseCacheSizeInMBytes, a3, 1u, &v6);
  if ( !a2 )
    return ZTraceReportOriginationNoThis(-2147467261, "MosHostGetBrowseCacheSizeInMBytes", 69);
  BrowseCacheSizeInMBytes = MosStorageGetBrowseCacheSizeInMBytes(a2);
  if ( BrowseCacheSizeInMBytes >= 0 )
    return 0;
  else
    return ZTraceReportPropagationNoThis(BrowseCacheSizeInMBytes, "MosHostGetBrowseCacheSizeInMBytes", 71);
}

```

## disassembly

```asm
0x180007550  push    rbx
0x180007552  sub     rsp, 50h
0x180007556  mov     rax, cs:__security_cookie
0x18000755d  xor     rax, rsp
0x180007560  mov     [rsp+58h+var_18], rax
0x180007565  mov     r9d, 1
0x18000756b  mov     rbx, rdx
0x18000756e  test    cs:Microsoft_Windows_MosHostEnableBits, r9b
0x180007575  jz      short loc_18000758D
0x180007577  lea     rax, [rsp+58h+var_28]
0x18000757c  lea     rdx, GetBrowseCacheSizeInMBytes
0x180007583  mov     [rsp+58h+var_38], rax
0x180007588  call    McGenEventWrite_EventWriteTransfer
0x18000758d  test    rbx, rbx
0x180007590  jnz     short loc_1800075AA
0x180007592  lea     r8d, [rbx+45h]
0x180007596  mov     ecx, 80004003h
0x18000759b  lea     rdx, aMoshostgetbrow; "MosHostGetBrowseCacheSizeInMBytes"
0x1800075a2  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x1800075a8  jmp     short loc_1800075D0
0x1800075aa  mov     rcx, rbx
0x1800075ad  call    cs:__imp_?MosStorageGetBrowseCacheSizeInMBytes@@YAJPEAK@Z; MosStorageGetBrowseCacheSizeInMBytes(ulong *)
0x1800075b3  test    eax, eax
0x1800075b5  jns     short loc_1800075CE
0x1800075b7  mov     r8d, 47h ; 'G'
0x1800075bd  lea     rdx, aMoshostgetbrow; "MosHostGetBrowseCacheSizeInMBytes"
0x1800075c4  mov     ecx, eax
0x1800075c6  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x1800075cc  jmp     short loc_1800075D0
0x1800075ce  xor     eax, eax
0x1800075d0  mov     rcx, [rsp+58h+var_18]
0x1800075d5  xor     rcx, rsp; StackCookie
0x1800075d8  call    __security_check_cookie
0x1800075dd  add     rsp, 50h
0x1800075e1  pop     rbx
0x1800075e2  retn
```
