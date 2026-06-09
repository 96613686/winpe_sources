# Perflib004Update

- ea: `0x180010f28`
- end: `0x18001117a`
- name: `Perflib004Update`
- size: `594`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180010430`

## callees

- `0x180005da0`
- `0x180008050`
- `0x1800102c0`
- `0x180010328`
- `0x180010f28`
- `0x180011568`
- `0x180011738`

## import_xrefs

- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18001100c`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180011060`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18001100c`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180011060`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180010f68`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180010fa9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180010f68`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180010fa9`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180010fdd`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180011113`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180010fdd`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180011113`

## pseudocode

```c
void __fastcall Perflib004Update(const unsigned __int16 *a1)
{
  WCHAR *v1; // rbx
  unsigned int LangIdFromSzLang; // eax
  int v3; // edi
  UINT SystemDirectoryW; // eax
  __int64 v5; // rsi
  WCHAR *v6; // rax
  const WCHAR *v7; // rdx
  unsigned int v8; // r15d
  unsigned __int16 *v9; // rbp
  int ThreadPreferredUILanguages; // eax
  __int64 v11; // rax
  unsigned __int16 *v12; // r14
  unsigned __int16 v13; // ax
  const unsigned __int16 *v14; // rsi
  unsigned int v15; // eax
  __int64 v16; // rax
  unsigned int v17; // [rsp+78h] [rbp+10h] BYREF
  int v18; // [rsp+80h] [rbp+18h] BYREF

  v1 = 0;
  LangIdFromSzLang = GetLangIdFromSzLang(a1);
  v17 = 0;
  v3 = LangIdFromSzLang;
  v18 = 0;
  if ( LangIdFromSzLang == 4 || LangIdFromSzLang == 22 )
  {
    SystemDirectoryW = GetSystemDirectoryW(0, 0);
    v5 = SystemDirectoryW;
    if ( SystemDirectoryW )
    {
      v6 = (WCHAR *)operator new(saturated_mul(SystemDirectoryW + 20, 2u));
      v1 = v6;
      if ( v6 )
      {
        if ( GetSystemDirectoryW(v6, v5 + 1) )
        {
          v7 = L"perfc004.dat";
          if ( v3 != 4 )
            v7 = L"perfc016.dat";
          if ( SearchPathW(v1, v7, 0, 0, 0, 0) )
          {
            v8 = v3;
            v9 = &v1[v5 + 1];
            ThreadPreferredUILanguages = RtlGetThreadPreferredUILanguages(36, &v18, 0, &v17);
            if ( !ThreadPreferredUILanguages || ThreadPreferredUILanguages == -1073741789 )
            {
              if ( v17 )
              {
                v11 = operator new(saturated_mul(v17, 2u));
                v12 = (unsigned __int16 *)v11;
                if ( v11 )
                {
                  RtlGetThreadPreferredUILanguages(36, &v18, v11, &v17);
                  if ( v18 )
                  {
                    v13 = *v12;
                    if ( *v12 )
                    {
                      v14 = v12;
                      while ( v13 )
                      {
                        v15 = GetLangIdFromSzLang(v14);
                        if ( (v15 & 0x3FF) == v3 )
                        {
                          v8 = v15;
                          break;
                        }
                        v16 = -1;
                        do
                          ++v16;
                        while ( v14[v16] );
                        v14 += v16 + 1;
                        v13 = *v14;
                      }
                    }
                  }
                  operator delete(v12);
                }
              }
            }
            PerfGetLangId(v8, 0, v9, 5u);
            StringCchPrintfW(v9 + 5, 0xEu, L"%ws%ws%ws", L"prfc", v9, L".dat");
            if ( SearchPathW(v1, v9 + 5, 0, 0, 0, 0) )
            {
              PerflibRename004File((__int64)v1, v3, (__int64)v9, 1);
              PerflibRename004File((__int64)v1, v3, (__int64)v9, 0);
              PerflibRename004File((__int64)v1, v3, 0, 1);
              PerflibRename004File((__int64)v1, v3, 0, 0);
            }
          }
        }
      }
    }
  }
  operator delete(v1);
}

```

## disassembly

```asm
0x180010f28  mov     [rsp+arg_0], rbx
0x180010f2d  push    rbp
0x180010f2e  push    rsi
0x180010f2f  push    rdi
0x180010f30  push    r12
0x180010f32  push    r13
0x180010f34  push    r14
0x180010f36  push    r15
0x180010f38  sub     rsp, 30h
0x180010f3c  xor     r13d, r13d
0x180010f3f  mov     ebx, r13d
0x180010f42  call    ?GetLangIdFromSzLang@@YAKPEBG@Z; GetLangIdFromSzLang(ushort const *)
0x180010f47  mov     [rsp+68h+arg_8], r13d
0x180010f4c  mov     edi, eax
0x180010f4e  mov     [rsp+68h+arg_10], r13d
0x180010f56  cmp     eax, 4
0x180010f59  jz      short loc_180010F64
0x180010f5b  cmp     eax, 16h
0x180010f5e  jnz     loc_18001115D
0x180010f64  xor     edx, edx; uSize
0x180010f66  xor     ecx, ecx; lpBuffer
0x180010f68  call    cs:__imp_GetSystemDirectoryW
0x180010f6e  mov     esi, eax
0x180010f70  test    eax, eax
0x180010f72  jz      loc_18001115D
0x180010f78  mov     r14d, 2
0x180010f7e  lea     ecx, [rsi+14h]
0x180010f81  mov     eax, r14d
0x180010f84  mul     rcx
0x180010f87  lea     rcx, [r14-3]
0x180010f8b  cmovb   rax, rcx
0x180010f8f  mov     rcx, rax
0x180010f92  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180010f97  mov     rbx, rax
0x180010f9a  test    rax, rax
0x180010f9d  jz      loc_18001115D
0x180010fa3  lea     edx, [rsi+1]; uSize
0x180010fa6  mov     rcx, rax; lpBuffer
0x180010fa9  call    cs:__imp_GetSystemDirectoryW
0x180010faf  test    eax, eax
0x180010fb1  jz      loc_18001115D
0x180010fb7  xor     r9d, r9d; nBufferLength
0x180010fba  mov     [rsp+68h+lpFilePart], r13; lpFilePart
0x180010fbf  xor     r8d, r8d; lpExtension
0x180010fc2  mov     [rsp+68h+lpBuffer], r13; lpBuffer
0x180010fc7  lea     rdx, aPerfc004Dat; "perfc004.dat"
0x180010fce  mov     rcx, rbx; lpPath
0x180010fd1  cmp     edi, 4
0x180010fd4  jz      short loc_180010FDD
0x180010fd6  lea     rdx, FileName; "perfc016.dat"
0x180010fdd  call    cs:__imp_SearchPathW
0x180010fe3  test    eax, eax
0x180010fe5  jz      loc_18001115D
0x180010feb  lea     rax, [rsi+1]
0x180010fef  xor     r8d, r8d
0x180010ff2  lea     r9, [rsp+68h+arg_8]
0x180010ff7  mov     r15d, edi
0x180010ffa  lea     rdx, [rsp+68h+arg_10]
0x180011002  lea     rbp, [rbx+rax*2]
0x180011006  lea     esi, [r8+24h]
0x18001100a  mov     ecx, esi
0x18001100c  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x180011012  test    eax, eax
0x180011014  jz      short loc_180011021
0x180011016  cmp     eax, 0C0000023h
0x18001101b  jnz     loc_1800110BC
0x180011021  mov     ecx, [rsp+68h+arg_8]
0x180011025  test    ecx, ecx
0x180011027  jz      loc_1800110BC
0x18001102d  mov     rax, r14
0x180011030  mul     rcx
0x180011033  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001103a  cmovb   rax, rcx
0x18001103e  mov     rcx, rax
0x180011041  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180011046  mov     r14, rax
0x180011049  test    rax, rax
0x18001104c  jz      short loc_1800110BC
0x18001104e  lea     r9, [rsp+68h+arg_8]
0x180011053  mov     r8, rax
0x180011056  lea     rdx, [rsp+68h+arg_10]
0x18001105e  mov     ecx, esi
0x180011060  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x180011066  cmp     [rsp+68h+arg_10], r13d
0x18001106e  jbe     short loc_1800110B4
0x180011070  movzx   eax, word ptr [r14]
0x180011074  test    ax, ax
0x180011077  jz      short loc_1800110B4
0x180011079  mov     rsi, r14
0x18001107c  test    ax, ax
0x18001107f  jz      short loc_1800110B4
0x180011081  mov     rcx, rsi; unsigned __int16 *
0x180011084  call    ?GetLangIdFromSzLang@@YAKPEBG@Z; GetLangIdFromSzLang(ushort const *)
0x180011089  movzx   ecx, ax
0x18001108c  and     ecx, 3FFh
0x180011092  cmp     ecx, edi
0x180011094  jz      short loc_1800110B1
0x180011096  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001109a  inc     rax
0x18001109d  cmp     [rsi+rax*2], r13w
0x1800110a2  jnz     short loc_18001109A
0x1800110a4  lea     rsi, [rsi+rax*2]
0x1800110a8  add     rsi, 2
0x1800110ac  movzx   eax, word ptr [rsi]
0x1800110af  jmp     short loc_18001107C
0x1800110b1  mov     r15d, eax
0x1800110b4  mov     rcx, r14; Block
0x1800110b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800110bc  mov     r9d, 5; unsigned int
0x1800110c2  mov     r8, rbp; unsigned __int16 *
0x1800110c5  xor     edx, edx; unsigned __int8
0x1800110c7  mov     ecx, r15d; unsigned int
0x1800110ca  call    ?PerfGetLangId@@YAXKEPEAGK@Z; PerfGetLangId(ulong,uchar,ushort *,ulong)
0x1800110cf  lea     r8, aDat; ".dat"
0x1800110d6  mov     edx, 0Eh; unsigned __int64
0x1800110db  mov     [rsp+68h+lpFilePart], r8
0x1800110e0  lea     r9, aPrfc; "prfc"
0x1800110e7  lea     r8, aWsWsWs; "%ws%ws%ws"
0x1800110ee  mov     [rsp+68h+lpBuffer], rbp
0x1800110f3  lea     rcx, [rbp+0Ah]; unsigned __int16 *
0x1800110f7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800110fc  xor     r9d, r9d; nBufferLength
0x1800110ff  mov     [rsp+68h+lpFilePart], r13; lpFilePart
0x180011104  xor     r8d, r8d; lpExtension
0x180011107  mov     [rsp+68h+lpBuffer], r13; lpBuffer
0x18001110c  lea     rdx, [rbp+0Ah]; lpFileName
0x180011110  mov     rcx, rbx; lpPath
0x180011113  call    cs:__imp_SearchPathW
0x180011119  test    eax, eax
0x18001111b  jz      short loc_18001115D
0x18001111d  mov     r9b, 1
0x180011120  mov     r8, rbp
0x180011123  mov     edx, edi
0x180011125  mov     rcx, rbx
0x180011128  call    PerflibRename004File
0x18001112d  xor     r9d, r9d
0x180011130  mov     r8, rbp
0x180011133  mov     edx, edi
0x180011135  mov     rcx, rbx
0x180011138  call    PerflibRename004File
0x18001113d  mov     r9b, 1
0x180011140  xor     r8d, r8d
0x180011143  mov     edx, edi
0x180011145  mov     rcx, rbx
0x180011148  call    PerflibRename004File
0x18001114d  xor     r9d, r9d
0x180011150  xor     r8d, r8d
0x180011153  mov     edx, edi
0x180011155  mov     rcx, rbx
0x180011158  call    PerflibRename004File
0x18001115d  mov     rcx, rbx; Block
0x180011160  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011165  mov     rbx, [rsp+68h+arg_0]
0x18001116a  add     rsp, 30h
0x18001116e  pop     r15
0x180011170  pop     r14
0x180011172  pop     r13
0x180011174  pop     r12
0x180011176  pop     rdi
0x180011177  pop     rsi
0x180011178  pop     rbp
0x180011179  retn
```
