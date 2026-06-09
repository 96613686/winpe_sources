# TpmApiCreateContext

- ea: `0x18001c5b4`
- end: `0x18001c89f`
- name: `TpmApiCreateContext`
- size: `747`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800107e8`
- `0x180032f1c`

## callees

- `0x18001c5b4`
- `0x18001cc1c`
- `0x18001cea8`
- `0x18001ced4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c658`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c658`
- `tbs!Tbsi_Context_Create` at `0x18001c73e`
- `tbs!Tbsi_Context_Create` at `0x18001c73e`

## pseudocode

```c
__int64 __fastcall TpmApiCreateContext(_DWORD *a1, __int64 *a2)
{
  signed int v4; // ebx
  _DWORD *v5; // rsi
  _DWORD *v6; // r14
  unsigned int v7; // ecx
  int v8; // eax
  PVOID phContext; // [rsp+28h] [rbp-20h] BYREF
  __int64 v11; // [rsp+60h] [rbp+18h] BYREF
  __int64 pContextParams; // [rsp+68h] [rbp+20h] BYREF

  phContext = 0;
  pContextParams = 0;
  v11 = 0;
  g_fpGetMemory = (void *(*)(unsigned __int64))TpmApiPlatformGetMemory;
  g_fpFreeMemory = (void (*)(void *))TpmApiPlatformFreeMemory;
  g_fpW8TpmSubmit = (unsigned int (*)(void *, unsigned __int8 *const, unsigned int, unsigned __int8 *, unsigned int *))TpmApiPlatformW8TbsSubmit;
  g_fpGetRandom = (int (*)(unsigned __int8 *, unsigned int))TpmApiPlatformGetRandom;
  g_fpHash = (int (*)(unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *, unsigned int))TpmApiPlatformHash;
  g_fpAesCfbEncrypt = (int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *))TpmApiPlatformAesCfbEncrypt;
  g_fpAesCfbDecrypt = (int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *))TpmApiPlatformAesCfbDecrypt;
  InitOnceExecuteOnce(&g_CallbackInitOnce, CheckAndInitCallbacksOnce, 0, 0);
  if ( a1 )
  {
    if ( a2 )
    {
      *a2 = 0;
      if ( *a1 == 12 && (v5 = a1 + 1, a1[1] == 1) && (v6 = a1 + 2, v7 = a1[2], v7 < 0x80000000) )
      {
        v8 = 1;
      }
      else
      {
        if ( *a1 != 16 || (v5 = a1 + 1, a1[1] != 2) || (v6 = a1 + 2, v7 = a1[2], v7 >= 0x80000000) )
        {
          v4 = -2144796395;
          goto LABEL_36;
        }
        v8 = 2;
      }
      if ( v8 == 2 )
      {
        LODWORD(pContextParams) = 2;
        HIDWORD(pContextParams) = a1[3] | 4;
      }
      else if ( dword_180072B40 == 2 )
      {
        pContextParams = 0x400000002LL;
        v6 = a1 + 2;
        v5 = a1 + 1;
      }
      else
      {
        LODWORD(pContextParams) = 1;
      }
      if ( !v7 || (v4 = Tbsi_Context_Create((PCTBS_CONTEXT_PARAMS)&pContextParams, &phContext), v4 >= 0) )
      {
        v4 = TpmApiCallbackAlloc(0, 32, &v11);
        if ( v4 >= 0 )
        {
          *(_DWORD *)v11 = 541278548;
          *(_DWORD *)(v11 + 4) = 24;
          *(_DWORD *)(v11 + 8) = 0;
          *(_DWORD *)(v11 + 12) = *v6;
          *(_QWORD *)(v11 + 16) = phContext;
          if ( *v5 == 2 || dword_180072B40 == 2 )
          {
            *(_DWORD *)(v11 + 4) = 32;
            *(_DWORD *)(v11 + 24) = HIDWORD(pContextParams);
          }
          if ( v11 )
          {
            if ( *(_DWORD *)v11 == 541278548 )
            {
              if ( ((*(_DWORD *)(v11 + 4) - 24) & 0xFFFFFFF7) != 0 )
              {
                v4 = -2144796395;
              }
              else if ( *(_DWORD *)(v11 + 8) )
              {
                v4 = -2144796395;
              }
              else if ( *(_DWORD *)(v11 + 12) < 0x80000000 )
              {
                *a2 = v11 ^ 0x1D9C0E3A;
                v11 = 0;
              }
              else
              {
                v4 = -2144796395;
              }
            }
            else
            {
              v4 = -2144796395;
            }
          }
          else
          {
            v4 = -2144796412;
          }
        }
      }
    }
    else
    {
      v4 = -2144796413;
    }
  }
  else
  {
    v4 = -2144796412;
  }
LABEL_36:
  TpmApiCallbackFree(0, 24);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001c5b4  mov     rax, rsp
0x18001c5b7  mov     [rax+8], rbx
0x18001c5bb  push    rsi
0x18001c5bc  push    r14
0x18001c5be  push    r15
0x18001c5c0  sub     rsp, 30h
0x18001c5c4  mov     r15, rdx
0x18001c5c7  mov     rbx, rcx
0x18001c5ca  mov     qword ptr [rax-20h], 0
0x18001c5d2  mov     qword ptr [rax+20h], 0
0x18001c5da  mov     qword ptr [rax+18h], 0
0x18001c5e2  lea     rax, ?TpmApiPlatformGetMemory@@YAPEAX_K@Z; TpmApiPlatformGetMemory(unsigned __int64)
0x18001c5e9  mov     cs:?g_fpGetMemory@@3P6APEAX_K@ZEA, rax; void * (*g_fpGetMemory)(unsigned __int64)
0x18001c5f0  lea     rax, ?TpmApiPlatformFreeMemory@@YAXPEAX@Z; TpmApiPlatformFreeMemory(void *)
0x18001c5f7  mov     cs:?g_fpFreeMemory@@3P6AXPEAX@ZEA, rax; void (*g_fpFreeMemory)(void *)
0x18001c5fe  lea     rax, ?TpmApiPlatformW8TbsSubmit@@YAIPEAXQEAEIPEAEPEAI@Z; TpmApiPlatformW8TbsSubmit(void *,uchar * const,uint,uchar *,uint *)
0x18001c605  mov     cs:?g_fpW8TpmSubmit@@3P6AIPEAXQEAEIPEAEPEAI@ZEA, rax; uint (*g_fpW8TpmSubmit)(void *,uchar * const,uint,uchar *,uint *)
0x18001c60c  lea     rax, ?TpmApiPlatformGetRandom@@YAJPEAEI@Z; TpmApiPlatformGetRandom(uchar *,uint)
0x18001c613  mov     cs:?g_fpGetRandom@@3P6AJPEAEI@ZEA, rax; long (*g_fpGetRandom)(uchar *,uint)
0x18001c61a  lea     rax, ?TpmApiPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z; TpmApiPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x18001c621  mov     cs:?g_fpHash@@3P6AJPEAGPEAEI1I1IPEAIK@ZEA, rax; long (*g_fpHash)(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x18001c628  lea     rax, ?TpmApiPlatformAesCfbEncrypt@@YAJPEAEI0I0I0@Z; TpmApiPlatformAesCfbEncrypt(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x18001c62f  mov     cs:?g_fpAesCfbEncrypt@@3P6AJPEAEI0I0I0@ZEA, rax; long (*g_fpAesCfbEncrypt)(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x18001c636  lea     rax, ?TpmApiPlatformAesCfbDecrypt@@YAJPEAEI0I0I0@Z; TpmApiPlatformAesCfbDecrypt(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x18001c63d  mov     cs:?g_fpAesCfbDecrypt@@3P6AJPEAEI0I0I0@ZEA, rax; long (*g_fpAesCfbDecrypt)(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x18001c644  xor     r9d, r9d; Context
0x18001c647  xor     r8d, r8d; Parameter
0x18001c64a  lea     rdx, ?CheckAndInitCallbacksOnce@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001c651  lea     rcx, ?g_CallbackInitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18001c658  call    cs:__imp_InitOnceExecuteOnce
0x18001c65f  nop     dword ptr [rax+rax+00h]
0x18001c664  test    rbx, rbx
0x18001c667  jnz     short loc_18001C67C
0x18001c669  mov     ebx, 80290104h
0x18001c66e  mov     [rsp+48h+var_28], ebx
0x18001c672  mov     r8, [rsp+48h+arg_10]
0x18001c677  jmp     loc_18001C881
0x18001c67c  test    r15, r15
0x18001c67f  jnz     short loc_18001C694
0x18001c681  mov     ebx, 80290103h
0x18001c686  mov     [rsp+48h+var_28], ebx
0x18001c68a  mov     r8, [rsp+48h+arg_10]
0x18001c68f  jmp     loc_18001C881
0x18001c694  xor     eax, eax
0x18001c696  mov     [r15], rax
0x18001c699  cmp     dword ptr [rbx], 0Ch
0x18001c69c  jnz     short loc_18001C6BD
0x18001c69e  lea     rsi, [rbx+4]
0x18001c6a2  cmp     dword ptr [rsi], 1
0x18001c6a5  jnz     short loc_18001C6BD
0x18001c6a7  lea     r14, [rbx+8]
0x18001c6ab  mov     ecx, [r14]
0x18001c6ae  cmp     ecx, 80000000h
0x18001c6b4  jnb     short loc_18001C6BD
0x18001c6b6  mov     eax, 1
0x18001c6bb  jmp     short loc_18001C6EB
0x18001c6bd  cmp     dword ptr [rbx], 10h
0x18001c6c0  jnz     loc_18001C862
0x18001c6c6  lea     rsi, [rbx+4]
0x18001c6ca  cmp     dword ptr [rsi], 2
0x18001c6cd  jnz     loc_18001C862
0x18001c6d3  lea     r14, [rbx+8]
0x18001c6d7  mov     ecx, [r14]
0x18001c6da  cmp     ecx, 80000000h
0x18001c6e0  jnb     loc_18001C862
0x18001c6e6  mov     eax, 2
0x18001c6eb  cmp     eax, 2
0x18001c6ee  jnz     short loc_18001C704
0x18001c6f0  mov     dword ptr [rsp+48h+pContextParams], eax
0x18001c6f4  mov     eax, [rbx+0Ch]
0x18001c6f7  mov     dword ptr [rsp+48h+pContextParams+4], eax
0x18001c6fb  or      eax, 4
0x18001c6fe  mov     dword ptr [rsp+48h+pContextParams+4], eax
0x18001c702  jmp     short loc_18001C730
0x18001c704  cmp     cs:dword_180072B40, 2
0x18001c70b  jnz     short loc_18001C728
0x18001c70d  mov     [rsp+48h+pContextParams], 2
0x18001c716  mov     dword ptr [rsp+48h+pContextParams+4], 4
0x18001c71e  lea     r14, [rbx+8]
0x18001c722  lea     rsi, [rbx+4]
0x18001c726  jmp     short loc_18001C730
0x18001c728  mov     dword ptr [rsp+48h+pContextParams], 1
0x18001c730  test    ecx, ecx
0x18001c732  jz      short loc_18001C75E
0x18001c734  lea     rdx, [rsp+48h+phContext]; phContext
0x18001c739  lea     rcx, [rsp+48h+pContextParams]; pContextParams
0x18001c73e  call    cs:__imp_Tbsi_Context_Create
0x18001c745  nop     dword ptr [rax+rax+00h]
0x18001c74a  mov     ebx, eax
0x18001c74c  mov     [rsp+48h+var_28], eax
0x18001c750  test    eax, eax
0x18001c752  jns     short loc_18001C75E
0x18001c754  mov     r8, [rsp+48h+arg_10]
0x18001c759  jmp     loc_18001C881
0x18001c75e  lea     r8, [rsp+48h+arg_10]
0x18001c763  mov     edx, 20h ; ' '
0x18001c768  xor     ecx, ecx
0x18001c76a  call    TpmApiCallbackAlloc
0x18001c76f  mov     ebx, eax
0x18001c771  mov     [rsp+48h+var_28], eax
0x18001c775  test    eax, eax
0x18001c777  jns     short loc_18001C783
0x18001c779  mov     r8, [rsp+48h+arg_10]
0x18001c77e  jmp     loc_18001C881
0x18001c783  mov     edx, 20434154h
0x18001c788  mov     rax, [rsp+48h+arg_10]
0x18001c78d  mov     [rax], edx
0x18001c78f  mov     rax, [rsp+48h+arg_10]
0x18001c794  mov     dword ptr [rax+4], 18h
0x18001c79b  mov     rax, [rsp+48h+arg_10]
0x18001c7a0  mov     dword ptr [rax+8], 0
0x18001c7a7  mov     ecx, [r14]
0x18001c7aa  mov     rax, [rsp+48h+arg_10]
0x18001c7af  mov     [rax+0Ch], ecx
0x18001c7b2  mov     rcx, [rsp+48h+phContext]
0x18001c7b7  mov     rax, [rsp+48h+arg_10]
0x18001c7bc  mov     [rax+10h], rcx
0x18001c7c0  cmp     dword ptr [rsi], 2
0x18001c7c3  jz      short loc_18001C7CE
0x18001c7c5  cmp     cs:dword_180072B40, 2
0x18001c7cc  jnz     short loc_18001C7E6
0x18001c7ce  mov     rax, [rsp+48h+arg_10]
0x18001c7d3  mov     dword ptr [rax+4], 20h ; ' '
0x18001c7da  mov     rax, [rsp+48h+arg_10]
0x18001c7df  mov     ecx, dword ptr [rsp+48h+pContextParams+4]
0x18001c7e3  mov     [rax+18h], ecx
0x18001c7e6  mov     r8, [rsp+48h+arg_10]
0x18001c7eb  test    r8, r8
0x18001c7ee  jnz     short loc_18001C7FE
0x18001c7f0  mov     ebx, 80290104h
0x18001c7f5  mov     [rsp+48h+var_28], ebx
0x18001c7f9  jmp     loc_18001C881
0x18001c7fe  cmp     [r8], edx
0x18001c801  jz      short loc_18001C80E
0x18001c803  mov     ebx, 80290115h
0x18001c808  mov     [rsp+48h+var_28], ebx
0x18001c80c  jmp     short loc_18001C881
0x18001c80e  mov     eax, [r8+4]
0x18001c812  sub     eax, 18h
0x18001c815  test    eax, 0FFFFFFF7h
0x18001c81a  jz      short loc_18001C827
0x18001c81c  mov     ebx, 80290115h
0x18001c821  mov     [rsp+48h+var_28], ebx
0x18001c825  jmp     short loc_18001C881
0x18001c827  cmp     dword ptr [r8+8], 0
0x18001c82c  jz      short loc_18001C839
0x18001c82e  mov     ebx, 80290115h
0x18001c833  mov     [rsp+48h+var_28], ebx
0x18001c837  jmp     short loc_18001C881
0x18001c839  cmp     dword ptr [r8+0Ch], 80000000h
0x18001c841  jb      short loc_18001C84E
0x18001c843  mov     ebx, 80290115h
0x18001c848  mov     [rsp+48h+var_28], ebx
0x18001c84c  jmp     short loc_18001C881
0x18001c84e  xor     r8, 1D9C0E3Ah
0x18001c855  mov     [r15], r8
0x18001c858  xor     r8d, r8d
0x18001c85b  mov     [rsp+48h+arg_10], r8
0x18001c860  jmp     short loc_18001C881
0x18001c862  mov     ebx, 80290115h
0x18001c867  mov     [rsp+48h+var_28], ebx
0x18001c86b  mov     r8, [rsp+48h+arg_10]
0x18001c870  jmp     short loc_18001C881
0x18001c872  mov     ebx, eax
0x18001c874  bts     ebx, 1Ch
0x18001c878  mov     [rsp+48h+var_28], ebx
0x18001c87c  mov     r8, [rsp+48h+arg_10]
0x18001c881  mov     edx, 18h
0x18001c886  xor     ecx, ecx
0x18001c888  call    TpmApiCallbackFree
0x18001c88d  mov     eax, ebx
0x18001c88f  mov     rbx, [rsp+48h+arg_0]
0x18001c894  add     rsp, 30h
0x18001c898  pop     r15
0x18001c89a  pop     r14
0x18001c89c  pop     rsi
0x18001c89d  retn
0x180057829  push    rbp
0x18005782b  sub     rsp, 20h
0x18005782f  mov     rbp, rdx
0x180057832  mov     rax, [rcx]
0x180057835  cmp     dword ptr [rax], 0C0000005h
0x18005783b  jz      short loc_180057851
0x18005783d  cmp     dword ptr [rax], 80000002h
0x180057843  jz      short loc_180057851
0x180057845  cmp     dword ptr [rax], 0C0000008h
0x18005784b  jz      short loc_180057851
0x18005784d  xor     eax, eax
0x18005784f  jmp     short loc_180057856
0x180057851  mov     eax, 1
0x180057856  add     rsp, 20h
0x18005785a  pop     rbp
0x18005785b  retn
```
