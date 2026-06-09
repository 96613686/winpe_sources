# DfsADBlobCache::UnpackBlob(uchar *,ulong *)

- ea: `0x140008f48`
- end: `0x140009218`
- name: `?UnpackBlob@DfsADBlobCache@@QEAAKPEAEPEAK@Z`
- size: `720`
- prototype: `unsigned int __fastcall(DfsADBlobCache *__hidden this, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009220`

## callees

- `0x140007414`
- `0x140007640`
- `0x140007880`
- `0x140008d74`
- `0x140008f48`
- `0x1400096d8`
- `0x14000971c`
- `0x1400586a8`
- `0x140058e40`
- `0x140058e8c`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x1400090bf`
- `ntdll!RtlCompareUnicodeString` at `0x140009115`
- `ntdll!RtlCompareUnicodeString` at `0x1400090bf`
- `ntdll!RtlCompareUnicodeString` at `0x140009115`
- `ntdll!RtlInitUnicodeString` at `0x140009132`
- `ntdll!RtlInitUnicodeString` at `0x140009132`

## pseudocode

```c
__int64 __fastcall DfsADBlobCache::UnpackBlob(DfsADBlobCache *this, unsigned __int8 *a2, unsigned int *a3)
{
  unsigned int v3; // esi
  unsigned int inited; // ebx
  unsigned int i; // r15d
  unsigned int v7; // r14d
  unsigned __int8 *v8; // rsi
  _BYTE v10[8]; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int8 *v11; // [rsp+38h] [rbp-31h] BYREF
  struct _BLOB_DATA *v12; // [rsp+40h] [rbp-29h] BYREF
  UNICODE_STRING String1; // [rsp+48h] [rbp-21h] BYREF
  UNICODE_STRING String2; // [rsp+58h] [rbp-11h] BYREF
  UNICODE_STRING v15; // [rsp+68h] [rbp-1h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp+Fh] BYREF
  unsigned int v17; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned int v18; // [rsp+E0h] [rbp+77h] BYREF
  unsigned int v19; // [rsp+E8h] [rbp+7Fh] BYREF

  v18 = 0;
  v19 = 0;
  v3 = *a3;
  v12 = 0;
  String1 = 0;
  v11 = a2;
  String2 = 0;
  v17 = v3;
  v15 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x200) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_q(*((_QWORD *)pWppControl + 2), 35, WPP_5b055fab91a332e3ecfe0e73cd96251f_Traceguids, this);
  }
  inited = DfsRtlInitUnicodeStringEx(&String2, L"\\siteroot");
  if ( !inited )
  {
    inited = DfsRtlInitUnicodeStringEx(&v15, L"\\domainroot");
    if ( !inited )
    {
      *((_DWORD *)this + 10) = v3;
      _InterlockedIncrement((volatile signed __int32 *)this + 19);
      inited = PackGetULong(v10, &v11, &v17);
      if ( !inited )
      {
        if ( v17 )
        {
          inited = PackGetULong(&v18, &v11, &v17);
          if ( !inited )
          {
            for ( i = 0; i < v18; ++i )
            {
              inited = PackGetString(&String1, &v11, &v17);
              if ( !inited )
              {
                inited = PackGetULong(&v19, &v11, &v17);
                if ( !inited )
                {
                  v7 = v19;
                  if ( v19 <= v17 )
                  {
                    v8 = v11;
                    v17 -= v19;
                    v11 += v19;
                    if ( RtlCompareUnicodeString(&String1, &String2, 1u) )
                    {
                      if ( RtlCompareUnicodeString(&String1, &v15, 1u) )
                      {
                        inited = DfsADBlobCache::CheckAndFixCorruptBlob(this, &String1, v8, v7);
                        if ( !inited )
                        {
                          inited = DfsADBlobCache::StoreBlobInCache(this, &String1, v8, v7);
                          if ( inited )
                            break;
                        }
                      }
                      else
                      {
                        DestinationString = 0;
                        RtlInitUnicodeString(&DestinationString, 0);
                        inited = DfsADBlobCache::CreateBlob(this, &DestinationString, v8, v7, &v12);
                        if ( !inited )
                        {
                          DfsThreadpoolDeleteCallbackContext(*((struct _DFS_THREADPOOL_CALLBACK_CONTEXT **)this + 4));
                          *((_QWORD *)this + 4) = v12;
                        }
                      }
                    }
                    else
                    {
                      inited = DfsADBlobCache::CreateBlob(this, &String1, v8, v7, &v12);
                      if ( !inited )
                      {
                        DfsThreadpoolDeleteCallbackContext(*((struct _DFS_THREADPOOL_CALLBACK_CONTEXT **)this + 3));
                        *((_QWORD *)this + 3) = v12;
                      }
                    }
                  }
                  else
                  {
                    inited = 13;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (((1 << (inited != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_qd(*((_QWORD *)pWppControl + 2), 36, WPP_5b055fab91a332e3ecfe0e73cd96251f_Traceguids, this, inited);
  }
  return inited;
}

```

## disassembly

```asm
0x140008f48  push    rbp
0x140008f4a  push    rbx
0x140008f4b  push    rsi
0x140008f4c  push    rdi
0x140008f4d  push    r12
0x140008f4f  push    r14
0x140008f51  push    r15
0x140008f53  lea     rbp, [rsp-27h]
0x140008f58  sub     rsp, 90h
0x140008f5f  and     [rbp+57h+arg_10], 0
0x140008f63  xorps   xmm0, xmm0
0x140008f66  and     [rbp+57h+arg_18], 0
0x140008f6a  xorps   xmm1, xmm1
0x140008f6d  mov     esi, [r8]
0x140008f70  mov     rdi, rcx
0x140008f73  and     [rbp+57h+var_80], 0
0x140008f78  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x140008f7c  mov     [rbp+57h+var_88], rdx
0x140008f80  movups  xmmword ptr [rbp+57h+String2.Length], xmm1
0x140008f84  mov     [rbp+57h+arg_8], esi
0x140008f87  movups  xmmword ptr [rbp+57h+var_58.Length], xmm0
0x140008f8b  lea     rax, WPP_GLOBAL_Control
0x140008f92  mov     r12d, 200h
0x140008f98  cmp     cs:WPP_GLOBAL_Control, rax
0x140008f9f  jz      short loc_140008FD1
0x140008fa1  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140008fa8  test    rcx, rcx
0x140008fab  jz      short loc_140008FD1
0x140008fad  test    [rcx+1Ch], r12d
0x140008fb1  jz      short loc_140008FD1
0x140008fb3  cmp     byte ptr [rcx+19h], 3
0x140008fb7  jb      short loc_140008FD1
0x140008fb9  mov     rcx, [rcx+10h]
0x140008fbd  lea     r8, WPP_5b055fab91a332e3ecfe0e73cd96251f_Traceguids
0x140008fc4  mov     edx, 23h ; '#'
0x140008fc9  mov     r9, rdi
0x140008fcc  call    WPP_SF_q
0x140008fd1  lea     rdx, aSiteroot; "\\siteroot"
0x140008fd8  lea     rcx, [rbp+57h+String2]
0x140008fdc  call    DfsRtlInitUnicodeStringEx
0x140008fe1  mov     ebx, eax
0x140008fe3  test    eax, eax
0x140008fe5  jnz     loc_1400091AF
0x140008feb  lea     rdx, aDomainroot; "\\domainroot"
0x140008ff2  lea     rcx, [rbp+57h+var_58]
0x140008ff6  call    DfsRtlInitUnicodeStringEx
0x140008ffb  mov     ebx, eax
0x140008ffd  test    eax, eax
0x140008fff  jnz     loc_1400091AF
0x140009005  mov     [rdi+28h], esi
0x140009008  lock inc dword ptr [rdi+4Ch]
0x14000900c  lea     r8, [rbp+57h+arg_8]
0x140009010  lea     rdx, [rbp+57h+var_88]
0x140009014  lea     rcx, [rbp+57h+var_90]
0x140009018  call    PackGetULong
0x14000901d  mov     ebx, eax
0x14000901f  test    eax, eax
0x140009021  jnz     loc_1400091AF
0x140009027  cmp     [rbp+57h+arg_8], eax
0x14000902a  jz      loc_1400091AF
0x140009030  lea     r8, [rbp+57h+arg_8]
0x140009034  lea     rdx, [rbp+57h+var_88]
0x140009038  lea     rcx, [rbp+57h+arg_10]
0x14000903c  call    PackGetULong
0x140009041  mov     ebx, eax
0x140009043  test    eax, eax
0x140009045  jnz     loc_1400091AF
0x14000904b  xor     r15d, r15d
0x14000904e  cmp     [rbp+57h+arg_10], r15d
0x140009052  jbe     loc_1400091AF
0x140009058  lea     r8, [rbp+57h+arg_8]
0x14000905c  lea     rdx, [rbp+57h+var_88]
0x140009060  lea     rcx, [rbp+57h+String1]
0x140009064  call    PackGetString
0x140009069  mov     ebx, eax
0x14000906b  test    eax, eax
0x14000906d  jnz     loc_1400091A2
0x140009073  lea     r8, [rbp+57h+arg_8]
0x140009077  lea     rdx, [rbp+57h+var_88]
0x14000907b  lea     rcx, [rbp+57h+arg_18]
0x14000907f  call    PackGetULong
0x140009084  mov     ebx, eax
0x140009086  test    eax, eax
0x140009088  jnz     loc_1400091A2
0x14000908e  mov     r14d, [rbp+57h+arg_18]
0x140009092  mov     ecx, [rbp+57h+arg_8]
0x140009095  cmp     r14d, ecx
0x140009098  jbe     short loc_1400090A2
0x14000909a  lea     ebx, [rax+0Dh]
0x14000909d  jmp     loc_1400091A2
0x1400090a2  mov     rsi, [rbp+57h+var_88]
0x1400090a6  lea     rdx, [rbp+57h+String2]; String2
0x1400090aa  sub     ecx, r14d
0x1400090ad  mov     r8b, 1; CaseInsensitive
0x1400090b0  mov     [rbp+57h+arg_8], ecx
0x1400090b3  lea     rcx, [rbp+57h+String1]; String1
0x1400090b7  lea     rax, [rsi+r14]
0x1400090bb  mov     [rbp+57h+var_88], rax
0x1400090bf  call    cs:__imp_RtlCompareUnicodeString
0x1400090c6  nop     dword ptr [rax+rax+00h]
0x1400090cb  test    eax, eax
0x1400090cd  jnz     short loc_14000910A
0x1400090cf  lea     rax, [rbp+57h+var_80]
0x1400090d3  mov     r9d, r14d; unsigned int
0x1400090d6  mov     r8, rsi; unsigned __int8 *
0x1400090d9  mov     [rsp+0C0h+var_A0], rax; struct _BLOB_DATA **
0x1400090de  lea     rdx, [rbp+57h+String1]; struct _UNICODE_STRING *
0x1400090e2  mov     rcx, rdi; this
0x1400090e5  call    ?CreateBlob@DfsADBlobCache@@QEAAKPEAU_UNICODE_STRING@@PEAEKPEAPEAU_BLOB_DATA@@@Z; DfsADBlobCache::CreateBlob(_UNICODE_STRING *,uchar *,ulong,_BLOB_DATA * *)
0x1400090ea  mov     ebx, eax
0x1400090ec  test    eax, eax
0x1400090ee  jnz     loc_1400091A2
0x1400090f4  mov     rcx, [rdi+18h]; struct _DFS_THREADPOOL_CALLBACK_CONTEXT *
0x1400090f8  call    ?DfsThreadpoolDeleteCallbackContext@@YAXPEAU_DFS_THREADPOOL_CALLBACK_CONTEXT@@@Z; DfsThreadpoolDeleteCallbackContext(_DFS_THREADPOOL_CALLBACK_CONTEXT *)
0x1400090fd  mov     rax, [rbp+57h+var_80]
0x140009101  mov     [rdi+18h], rax
0x140009105  jmp     loc_1400091A2
0x14000910a  mov     r8b, 1; CaseInsensitive
0x14000910d  lea     rdx, [rbp+57h+var_58]; String2
0x140009111  lea     rcx, [rbp+57h+String1]; String1
0x140009115  call    cs:__imp_RtlCompareUnicodeString
0x14000911c  nop     dword ptr [rax+rax+00h]
0x140009121  test    eax, eax
0x140009123  jnz     short loc_140009172
0x140009125  xorps   xmm0, xmm0
0x140009128  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000912c  xor     edx, edx; SourceString
0x14000912e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140009132  call    cs:__imp_RtlInitUnicodeString
0x140009139  nop     dword ptr [rax+rax+00h]
0x14000913e  lea     rax, [rbp+57h+var_80]
0x140009142  mov     r9d, r14d; unsigned int
0x140009145  mov     r8, rsi; unsigned __int8 *
0x140009148  mov     [rsp+0C0h+var_A0], rax; struct _BLOB_DATA **
0x14000914d  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x140009151  mov     rcx, rdi; this
0x140009154  call    ?CreateBlob@DfsADBlobCache@@QEAAKPEAU_UNICODE_STRING@@PEAEKPEAPEAU_BLOB_DATA@@@Z; DfsADBlobCache::CreateBlob(_UNICODE_STRING *,uchar *,ulong,_BLOB_DATA * *)
0x140009159  mov     ebx, eax
0x14000915b  test    eax, eax
0x14000915d  jnz     short loc_1400091A2
0x14000915f  mov     rcx, [rdi+20h]; struct _DFS_THREADPOOL_CALLBACK_CONTEXT *
0x140009163  call    ?DfsThreadpoolDeleteCallbackContext@@YAXPEAU_DFS_THREADPOOL_CALLBACK_CONTEXT@@@Z; DfsThreadpoolDeleteCallbackContext(_DFS_THREADPOOL_CALLBACK_CONTEXT *)
0x140009168  mov     rax, [rbp+57h+var_80]
0x14000916c  mov     [rdi+20h], rax
0x140009170  jmp     short loc_1400091A2
0x140009172  mov     r9d, r14d; unsigned int
0x140009175  lea     rdx, [rbp+57h+String1]; struct _UNICODE_STRING *
0x140009179  mov     r8, rsi; unsigned __int8 *
0x14000917c  mov     rcx, rdi; this
0x14000917f  call    ?CheckAndFixCorruptBlob@DfsADBlobCache@@AEAAKPEAU_UNICODE_STRING@@PEAEK@Z; DfsADBlobCache::CheckAndFixCorruptBlob(_UNICODE_STRING *,uchar *,ulong)
0x140009184  mov     ebx, eax
0x140009186  test    eax, eax
0x140009188  jnz     short loc_1400091A2
0x14000918a  mov     r9d, r14d; unsigned int
0x14000918d  lea     rdx, [rbp+57h+String1]; struct _UNICODE_STRING *
0x140009191  mov     r8, rsi; unsigned __int8 *
0x140009194  mov     rcx, rdi; this
0x140009197  call    ?StoreBlobInCache@DfsADBlobCache@@QEAAKPEAU_UNICODE_STRING@@PEAEK@Z; DfsADBlobCache::StoreBlobInCache(_UNICODE_STRING *,uchar *,ulong)
0x14000919c  mov     ebx, eax
0x14000919e  test    eax, eax
0x1400091a0  jnz     short loc_1400091AF
0x1400091a2  inc     r15d
0x1400091a5  cmp     r15d, [rbp+57h+arg_10]
0x1400091a9  jb      loc_140009058
0x1400091af  lea     rax, WPP_GLOBAL_Control
0x1400091b6  cmp     cs:WPP_GLOBAL_Control, rax
0x1400091bd  jz      short loc_140009203
0x1400091bf  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400091c6  test    rcx, rcx
0x1400091c9  jz      short loc_140009203
0x1400091cb  mov     eax, ebx
0x1400091cd  neg     eax
0x1400091cf  sbb     edx, edx
0x1400091d1  and     edx, 0FFFFFFECh
0x1400091d4  add     edx, 1Fh
0x1400091d7  bts     r12d, edx
0x1400091db  test    [rcx+1Ch], r12d
0x1400091df  jz      short loc_140009203
0x1400091e1  cmp     byte ptr [rcx+19h], 3
0x1400091e5  jb      short loc_140009203
0x1400091e7  mov     rcx, [rcx+10h]
0x1400091eb  lea     r8, WPP_5b055fab91a332e3ecfe0e73cd96251f_Traceguids
0x1400091f2  mov     edx, 24h ; '$'
0x1400091f7  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x1400091fb  mov     r9, rdi
0x1400091fe  call    WPP_SF_qd
0x140009203  mov     eax, ebx
0x140009205  add     rsp, 90h
0x14000920c  pop     r15
0x14000920e  pop     r14
0x140009210  pop     r12
0x140009212  pop     rdi
0x140009213  pop     rsi
0x140009214  pop     rbx
0x140009215  pop     rbp
0x140009216  retn
```
