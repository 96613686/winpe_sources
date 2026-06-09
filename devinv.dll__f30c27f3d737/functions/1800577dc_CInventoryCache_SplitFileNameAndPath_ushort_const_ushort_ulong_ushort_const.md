# CInventoryCache::SplitFileNameAndPath(ushort const *,ushort *,ulong,ushort const * *)

- ea: `0x1800577dc`
- end: `0x180057a74`
- name: `?SplitFileNameAndPath@CInventoryCache@@AEAAJPEBGPEAGKPEAPEBG@Z`
- size: `664`
- prototype: `int(CInventoryCache *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180056d08`

## callees

- `0x180006d02`
- `0x180007014`
- `0x1800577dc`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180057816`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180057816`

## string_xrefs

- `0x180057835`: `Full driver path expected instead of [%ws]`
- `0x180057888`: `Full driver path expected instead of [%ws]`
- `0x1800578bd`: `Full driver path expected instead of [%ws]`
- `0x180057842`: `CInventoryCache::SplitFileNameAndPath`
- `0x180057865`: `CInventoryCache::SplitFileNameAndPath`
- `0x180057951`: `CInventoryCache::SplitFileNameAndPath`
- `0x180057977`: `CInventoryCache::SplitFileNameAndPath`
- `0x1800579ec`: `CInventoryCache::SplitFileNameAndPath`
- `0x180057a12`: `CInventoryCache::SplitFileNameAndPath`
- `0x180057943`: `StringCchCopyN failed: 0x%x`

## pseudocode

```c
__int64 __fastcall CInventoryCache::SplitFileNameAndPath(
        CInventoryCache *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int64 a4,
        wchar_t **a5)
{
  unsigned __int16 *v5; // rbx
  const unsigned __int16 *v6; // rsi
  wchar_t *v7; // rax
  unsigned int v8; // ebx
  FILE *v9; // rax
  FILE *v10; // rax
  FILE *v11; // rax
  unsigned __int64 v12; // rcx
  __int64 v13; // rdx
  unsigned __int16 *v14; // rcx
  FILE *v15; // rax
  FILE *v16; // rax
  FILE *v17; // rax
  FILE *v19; // rax
  FILE *v20; // rax
  FILE *v21; // rax

  v5 = a3;
  v6 = a2;
  if ( a3 && a5 && a2 )
  {
    v7 = wcsrchr(a2, 0x5Cu);
    *a5 = v7;
    if ( v7 )
    {
      v12 = (unsigned __int64)((char *)v7 - (char *)v6) >> 1;
      *a5 = v7 + 1;
      if ( v12 <= 0x7FFFFFFE )
      {
        v13 = 260;
        do
        {
          if ( !v12 )
            break;
          if ( !*v6 )
            break;
          *v5++ = *v6++;
          --v12;
          --v13;
        }
        while ( v13 );
        v14 = v5 - 1;
        if ( v13 )
          v14 = v5;
        v8 = v13 == 0 ? 0x8007007A : 0;
        *v14 = 0;
        if ( v13 )
          return v8;
      }
      else
      {
        *v5 = 0;
        v8 = -2147024809;
      }
      AslLogCallPrintf(2, "CInventoryCache::SplitFileNameAndPath", 350, "StringCchCopyN failed: 0x%x", v8);
      if ( EnableDevInvStdErrLog )
      {
        v15 = o___acrt_iob_func_0(2u);
        fprintf(v15, "Error: %s, %u: ", "CInventoryCache::SplitFileNameAndPath", 350);
        v16 = o___acrt_iob_func_0(2u);
        fprintf(v16, "StringCchCopyN failed: 0x%x", v8);
        v17 = o___acrt_iob_func_0(2u);
        fprintf(v17, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "StringCchCopyN failed: 0x%x", v8);
    }
    else
    {
      v8 = -2147024809;
      AslLogCallPrintf(
        2,
        "CInventoryCache::SplitFileNameAndPath",
        327,
        "Full driver path expected instead of [%ws]",
        v6);
      if ( EnableDevInvStdErrLog )
      {
        v9 = o___acrt_iob_func_0(2u);
        fprintf(v9, "Error: %s, %u: ", "CInventoryCache::SplitFileNameAndPath", 327);
        v10 = o___acrt_iob_func_0(2u);
        fprintf(v10, "Full driver path expected instead of [%ws]", v6);
        v11 = o___acrt_iob_func_0(2u);
        fprintf(v11, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "Full driver path expected instead of [%ws]", v6);
    }
    return v8;
  }
  AslLogCallPrintf(2, "CInventoryCache::SplitFileNameAndPath", 315, "Unexpected NULL arguments in call to function");
  if ( EnableDevInvStdErrLog )
  {
    v19 = o___acrt_iob_func_0(2u);
    fprintf(v19, "Error: %s, %u: ", "CInventoryCache::SplitFileNameAndPath", 315);
    v20 = o___acrt_iob_func_0(2u);
    fprintf(v20, "Unexpected NULL arguments in call to function");
    v21 = o___acrt_iob_func_0(2u);
    fprintf(v21, "\n");
  }
  if ( g_DeviceMapLogFunction )
    TraceMessageCallback(0x2000000, "Unexpected NULL arguments in call to function");
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800577dc  push    rbx
0x1800577de  push    rbp
0x1800577df  push    rsi
0x1800577e0  push    rdi
0x1800577e1  sub     rsp, 38h
0x1800577e5  xor     ebp, ebp
0x1800577e7  mov     rbx, r8
0x1800577ea  mov     rsi, rdx
0x1800577ed  test    r8, r8
0x1800577f0  jz      loc_1800579DB
0x1800577f6  mov     rdi, [rsp+58h+arg_20]
0x1800577fe  test    rdi, rdi
0x180057801  jz      loc_1800579DB
0x180057807  test    rdx, rdx
0x18005780a  jz      loc_1800579DB
0x180057810  lea     edx, [rbp+5Ch]; Ch
0x180057813  mov     rcx, rsi; Str
0x180057816  call    cs:__imp_wcsrchr
0x18005781c  mov     [rdi], rax
0x18005781f  mov     rcx, rax
0x180057822  test    rax, rax
0x180057825  jnz     loc_1800578D3
0x18005782b  lea     edi, [rbp+2]
0x18005782e  mov     [rsp+58h+var_38], rsi
0x180057833  mov     ecx, edi
0x180057835  lea     r9, aFullDriverPath; "Full driver path expected instead of [%"...
0x18005783c  mov     r8d, 147h
0x180057842  lea     rdx, aCinventorycach_3; "CInventoryCache::SplitFileNameAndPath"
0x180057849  mov     ebx, 80070057h
0x18005784e  call    AslLogCallPrintf
0x180057853  cmp     cs:EnableDevInvStdErrLog, ebp
0x180057859  jz      short loc_1800578AD
0x18005785b  mov     ecx, edi; Ix
0x18005785d  call    _o___acrt_iob_func_0
0x180057862  mov     rcx, rax; Stream
0x180057865  lea     r8, aCinventorycach_3; "CInventoryCache::SplitFileNameAndPath"
0x18005786c  mov     r9d, 147h
0x180057872  lea     rdx, Format; "Error: %s, %u: "
0x180057879  call    fprintf
0x18005787e  mov     ecx, edi; Ix
0x180057880  call    _o___acrt_iob_func_0
0x180057885  mov     rcx, rax; Stream
0x180057888  lea     rdx, aFullDriverPath; "Full driver path expected instead of [%"...
0x18005788f  mov     r8, rsi
0x180057892  call    fprintf
0x180057897  mov     ecx, edi; Ix
0x180057899  call    _o___acrt_iob_func_0
0x18005789e  mov     rcx, rax; Stream
0x1800578a1  lea     rdx, asc_18011EAD8; "\n"
0x1800578a8  call    fprintf
0x1800578ad  cmp     cs:g_DeviceMapLogFunction, rbp
0x1800578b4  jz      loc_1800579D4
0x1800578ba  mov     r8, rsi
0x1800578bd  lea     rdx, aFullDriverPath; "Full driver path expected instead of [%"...
0x1800578c4  mov     ecx, 2000000h
0x1800578c9  call    TraceMessageCallback
0x1800578ce  jmp     loc_1800579D4
0x1800578d3  sub     rcx, rsi
0x1800578d6  add     rax, 2
0x1800578da  shr     rcx, 1
0x1800578dd  mov     [rdi], rax
0x1800578e0  mov     edi, 2
0x1800578e5  cmp     rcx, 7FFFFFFEh
0x1800578ec  jbe     short loc_1800578F8
0x1800578ee  mov     [rbx], bp
0x1800578f1  mov     ebx, 80070057h
0x1800578f6  jmp     short loc_180057943
0x1800578f8  mov     edx, 104h
0x1800578fd  test    rcx, rcx
0x180057900  jz      short loc_18005791C
0x180057902  movzx   eax, word ptr [rsi]
0x180057905  test    ax, ax
0x180057908  jz      short loc_18005791C
0x18005790a  mov     [rbx], ax
0x18005790d  add     rsi, rdi
0x180057910  add     rbx, rdi
0x180057913  dec     rcx
0x180057916  sub     rdx, 1
0x18005791a  jnz     short loc_1800578FD
0x18005791c  lea     rcx, [rbx-2]
0x180057920  test    rdx, rdx
0x180057923  mov     rax, rdx
0x180057926  cmovnz  rcx, rbx
0x18005792a  neg     rax
0x18005792d  sbb     ebx, ebx
0x18005792f  not     ebx
0x180057931  and     ebx, 8007007Ah
0x180057937  mov     [rcx], bp
0x18005793a  test    rdx, rdx
0x18005793d  jnz     loc_1800579D4
0x180057943  lea     rsi, aStringcchcopyn; "StringCchCopyN failed: 0x%x"
0x18005794a  mov     dword ptr [rsp+58h+var_38], ebx
0x18005794e  mov     r9, rsi
0x180057951  lea     rdx, aCinventorycach_3; "CInventoryCache::SplitFileNameAndPath"
0x180057958  mov     r8d, 15Eh
0x18005795e  mov     ecx, edi
0x180057960  call    AslLogCallPrintf
0x180057965  cmp     cs:EnableDevInvStdErrLog, ebp
0x18005796b  jz      short loc_1800579BB
0x18005796d  mov     ecx, edi; Ix
0x18005796f  call    _o___acrt_iob_func_0
0x180057974  mov     rcx, rax; Stream
0x180057977  lea     r8, aCinventorycach_3; "CInventoryCache::SplitFileNameAndPath"
0x18005797e  mov     r9d, 15Eh
0x180057984  lea     rdx, Format; "Error: %s, %u: "
0x18005798b  call    fprintf
0x180057990  mov     ecx, edi; Ix
0x180057992  call    _o___acrt_iob_func_0
0x180057997  mov     rcx, rax; Stream
0x18005799a  mov     r8d, ebx
0x18005799d  mov     rdx, rsi; Format
0x1800579a0  call    fprintf
0x1800579a5  mov     ecx, edi; Ix
0x1800579a7  call    _o___acrt_iob_func_0
0x1800579ac  mov     rcx, rax; Stream
0x1800579af  lea     rdx, asc_18011EAD8; "\n"
0x1800579b6  call    fprintf
0x1800579bb  cmp     cs:g_DeviceMapLogFunction, rbp
0x1800579c2  jz      short loc_1800579D4
0x1800579c4  mov     r8d, ebx
0x1800579c7  mov     rdx, rsi
0x1800579ca  mov     ecx, 2000000h
0x1800579cf  call    TraceMessageCallback
0x1800579d4  mov     eax, ebx
0x1800579d6  jmp     loc_180057A6B
0x1800579db  lea     rbx, aUnexpectedNull_0; "Unexpected NULL arguments in call to fu"...
0x1800579e2  mov     esi, 13Bh
0x1800579e7  mov     edi, 2
0x1800579ec  lea     rdx, aCinventorycach_3; "CInventoryCache::SplitFileNameAndPath"
0x1800579f3  mov     r9, rbx
0x1800579f6  mov     r8d, esi
0x1800579f9  mov     ecx, edi
0x1800579fb  call    AslLogCallPrintf
0x180057a00  cmp     cs:EnableDevInvStdErrLog, ebp
0x180057a06  jz      short loc_180057A50
0x180057a08  mov     ecx, edi; Ix
0x180057a0a  call    _o___acrt_iob_func_0
0x180057a0f  mov     rcx, rax; Stream
0x180057a12  lea     r8, aCinventorycach_3; "CInventoryCache::SplitFileNameAndPath"
0x180057a19  mov     r9d, esi
0x180057a1c  lea     rdx, Format; "Error: %s, %u: "
0x180057a23  call    fprintf
0x180057a28  mov     ecx, edi; Ix
0x180057a2a  call    _o___acrt_iob_func_0
0x180057a2f  mov     rcx, rax; Stream
0x180057a32  mov     rdx, rbx; Format
0x180057a35  call    fprintf
0x180057a3a  mov     ecx, edi; Ix
0x180057a3c  call    _o___acrt_iob_func_0
0x180057a41  mov     rcx, rax; Stream
0x180057a44  lea     rdx, asc_18011EAD8; "\n"
0x180057a4b  call    fprintf
0x180057a50  cmp     cs:g_DeviceMapLogFunction, rbp
0x180057a57  jz      short loc_180057A66
0x180057a59  mov     rdx, rbx
0x180057a5c  mov     ecx, 2000000h
0x180057a61  call    TraceMessageCallback
0x180057a66  mov     eax, 80070057h
0x180057a6b  add     rsp, 38h
0x180057a6f  pop     rdi
0x180057a70  pop     rsi
0x180057a71  pop     rbp
0x180057a72  pop     rbx
0x180057a73  retn
```
