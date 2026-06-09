# _CatDBInitJetDatabaseParams(unsigned __int64 *)

- ea: `0x180001264`
- end: `0x180001322`
- name: `?_CatDBInitJetDatabaseParams@@YAHPEA_K@Z`
- size: `190`
- prototype: `__int64 __fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180019fe0`

## callees

- `0x180001264`
- `0x1800015b0`
- `0x1800038f0`
- `0x180004a20`
- `0x18000a59c`
- `0x18000acbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800012ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800012ec`
- `ESENT!JetSetSystemParameterW` at `0x1800012ca`
- `ESENT!JetSetSystemParameterW` at `0x1800012ca`

## pseudocode

```c
__int64 __fastcall _CatDBInitJetDatabaseParams(unsigned __int64 *a1)
{
  unsigned int v1; // esi
  unsigned __int16 *v2; // rax
  unsigned int v3; // edx
  unsigned __int16 *v4; // rcx
  unsigned __int16 *v5; // rbx
  unsigned int v6; // r8d
  struct _DBJETPARAM near **v7; // rdi
  JET_ERR v8; // ebp
  DWORD v9; // eax
  int v11; // [rsp+28h] [rbp-30h]

  v1 = 1;
  v2 = _CatDBGetCatrootDirW(1);
  v5 = v2;
  if ( v2 )
  {
    qword_180031008 = (__int64)v2;
    v7 = &g_rgJetParams;
    qword_180031018 = (__int64)v2;
    qword_180031028 = (__int64)v2;
    while ( v7 < (struct _DBJETPARAM near **)&lpSrc )
    {
      v8 = JetSetSystemParameterW(&g_JetInstance, 0, *(_DWORD *)v7, *((unsigned int *)v7 + 1), (JET_PCWSTR)v7[1]);
      if ( (unsigned int)_CatDBJET_errFailure(v8) )
      {
        v9 = _CatDBMapJetError(v8);
        SetLastError(v9);
        v6 = 5866;
        goto LABEL_8;
      }
      v7 += 2;
    }
    goto LABEL_9;
  }
  v6 = 5845;
LABEL_8:
  ErrLog_LogError(v4, v3, v6, 0, 0, v11);
  v1 = 0;
  if ( v5 )
LABEL_9:
    _CatDBFree(v5);
  return v1;
}

```

## disassembly

```asm
0x180001264  push    rbx
0x180001266  push    rbp
0x180001267  push    rsi
0x180001268  push    rdi
0x180001269  sub     rsp, 38h
0x18000126d  mov     esi, 1
0x180001272  mov     ecx, esi; int
0x180001274  call    ?_CatDBGetCatrootDirW@@YAPEAGH@Z; _CatDBGetCatrootDirW(int)
0x180001279  mov     rbx, rax
0x18000127c  test    rax, rax
0x18000127f  jnz     short loc_180001289
0x180001281  mov     r8d, 16D5h
0x180001287  jmp     short loc_1800012F8
0x180001289  mov     cs:qword_180031008, rbx
0x180001290  lea     rdi, ?g_rgJetParams@@3PAU_DBJETPARAM@@A; _DBJETPARAM near * g_rgJetParams
0x180001297  mov     cs:qword_180031018, rbx
0x18000129e  mov     cs:qword_180031028, rbx
0x1800012a5  lea     rax, lpSrc
0x1800012ac  cmp     rdi, rax
0x1800012af  jnb     short loc_18000130F
0x1800012b1  mov     rax, [rdi+8]
0x1800012b5  lea     rcx, ?g_JetInstance@@3_KA; pinstance
0x1800012bc  mov     r9d, [rdi+4]; lParam
0x1800012c0  xor     edx, edx; sesid
0x1800012c2  mov     r8d, [rdi]; paramid
0x1800012c5  mov     [rsp+58h+szParam], rax; szParam
0x1800012ca  call    cs:__imp_JetSetSystemParameterW
0x1800012d0  mov     ecx, eax; int
0x1800012d2  mov     ebp, eax
0x1800012d4  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x1800012d9  test    eax, eax
0x1800012db  jnz     short loc_1800012E3
0x1800012dd  add     rdi, 10h
0x1800012e1  jmp     short loc_1800012A5
0x1800012e3  mov     ecx, ebp; int
0x1800012e5  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x1800012ea  mov     ecx, eax; dwErrCode
0x1800012ec  call    cs:__imp_SetLastError
0x1800012f2  mov     r8d, 16EAh; unsigned int
0x1800012f8  xor     r9d, r9d; unsigned int
0x1800012fb  mov     dword ptr [rsp+58h+szParam], 0; int
0x180001303  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180001308  xor     esi, esi
0x18000130a  test    rbx, rbx
0x18000130d  jz      short loc_180001317
0x18000130f  mov     rcx, rbx; void *
0x180001312  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x180001317  mov     eax, esi
0x180001319  add     rsp, 38h
0x18000131d  pop     rdi
0x18000131e  pop     rsi
0x18000131f  pop     rbp
0x180001320  pop     rbx
0x180001321  retn
```
