# CDefragOperation::_ReadDefragListFile(IVolume *,ushort *)

- ea: `0x18002ebe4`
- end: `0x18002eeea`
- name: `?_ReadDefragListFile@CDefragOperation@@IEAAJPEAUIVolume@@PEAG@Z`
- size: `774`
- prototype: `__int64 __fastcall(CDefragOperation *this, struct IVolume *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18002b840`
- `0x1800548f0`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18002ebe4`
- `0x180067b0a`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `msvcrt!fclose` at `0x18002ee11`
- `msvcrt!fclose` at `0x18002ee11`
- `msvcrt!fgetws` at `0x18002ed0a`
- `msvcrt!fgetws` at `0x18002ed0a`
- `msvcrt!_wfopen` at `0x18002ecb2`
- `msvcrt!_wfopen` at `0x18002ecb2`
- `msvcrt!free` at `0x18002ee95`
- `msvcrt!free` at `0x18002ee95`
- `msvcrt!malloc` at `0x18002ecd3`
- `msvcrt!malloc` at `0x18002ecd3`
- `msvcrt!realloc` at `0x18002ed51`
- `msvcrt!realloc` at `0x18002ed51`

## string_xrefs

- `0x18002ec2b`: `CDefragOperation::_ReadDefragListFile`

## pseudocode

```c
__int64 __fastcall CDefragOperation::_ReadDefragListFile(
        CDefragOperation *this,
        struct IVolume *a2,
        unsigned __int16 *a3)
{
  struct IVolume *v5; // rbx
  _WORD *v6; // r14
  __int16 v7; // ax
  FILE *v8; // r13
  __int16 v9; // ax
  unsigned int v10; // esi
  unsigned int v11; // r12d
  wchar_t *v12; // r15
  __int64 v13; // rdx
  _WORD *v14; // rax
  unsigned int v15; // edi
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  __int16 v18; // [rsp+24h] [rbp-DCh]
  __int16 v19; // [rsp+26h] [rbp-DAh]
  struct IVolume *v20; // [rsp+58h] [rbp-A8h]
  CDefragOperation *v21; // [rsp+60h] [rbp-A0h]
  wchar_t Buffer[1024]; // [rsp+70h] [rbp-90h] BYREF

  v21 = this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "CDefragOperation::_ReadDefragListFile", 0x50Cu, 1u);
  v5 = 0;
  v20 = 0;
  v6 = 0;
  v7 = 1305;
  if ( !a3 )
  {
    v17 = -2147024809;
LABEL_34:
    v19 = v7;
    goto LABEL_35;
  }
  v17 = 0;
  v18 = 1305;
  if ( a2 )
    (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)a2 + 8LL))(a2);
  v5 = a2;
  v20 = a2;
  v17 = (*(__int64 (__fastcall **)(struct IVolume *))(*(_QWORD *)a2 + 352LL))(a2);
  v7 = 1309;
  if ( v17 < 0 )
    goto LABEL_34;
  v18 = 1309;
  v8 = _wfopen(a3, L"rt, ccs=UNICODE");
  if ( v8 )
  {
    v18 = 1313;
    v6 = malloc(0x208u);
    v9 = 1316;
    if ( v6 )
    {
      v10 = 0;
      v17 = 0;
      v18 = 1316;
      v11 = 260;
      while ( fgetws(Buffer, 1024, v8) )
      {
        v12 = Buffer;
        v13 = 0;
        while ( *v12 )
        {
          if ( *v12 == 10 )
          {
            if ( v10 )
            {
              v6[v10] = 0;
              v17 = (*(__int64 (__fastcall **)(struct IVolume *, _WORD *))(*(_QWORD *)a2 + 336LL))(a2, v6);
              v9 = 1346;
              if ( v17 < 0 )
                goto LABEL_25;
              v18 = 1346;
              memset_0(v6, 0, 2LL * v11);
              v10 = 0;
            }
          }
          else if ( *v12 != 13 )
          {
            if ( v10 >= v11 - 1 )
            {
              v11 *= 2;
              v14 = realloc(v6, 2LL * v11);
              v13 = 0;
              if ( !v14 )
              {
                v9 = 1332;
                goto LABEL_24;
              }
              v17 = 0;
              v18 = 1332;
              v6 = v14;
            }
            v6[v10++] = *v12;
          }
          v17 = (*(__int64 (__fastcall **)(CDefragOperation *, __int64))(*(_QWORD *)v21 + 32LL))(v21, v13);
          v13 = 0;
          v9 = 1353;
          if ( v17 < 0 )
            goto LABEL_25;
          v18 = 1353;
          ++v12;
        }
      }
      if ( v10 )
      {
        v6[v10] = 0;
        v17 = (*(__int64 (__fastcall **)(struct IVolume *, _WORD *))(*(_QWORD *)a2 + 336LL))(a2, v6);
        v9 = 1361;
        if ( v17 < 0 )
          goto LABEL_25;
        v18 = 1361;
      }
      v17 = (*(__int64 (__fastcall **)(struct IVolume *))(*(_QWORD *)a2 + 344LL))(a2);
      v9 = 1364;
      if ( v17 >= 0 )
      {
        v18 = 1364;
        v17 = 0;
        goto LABEL_26;
      }
    }
    else
    {
LABEL_24:
      v17 = -2147024882;
    }
LABEL_25:
    v19 = v9;
LABEL_26:
    fclose(v8);
    goto LABEL_35;
  }
  v17 = -1996488656;
  v19 = 1313;
LABEL_35:
  free(v6);
  v15 = v17;
  if ( v5 )
    (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)v5 + 16LL))(v5);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return v15;
}

```

## disassembly

```asm
0x18002ebe4  mov     [rsp-8+arg_18], rbx
0x18002ebe9  push    rbp
0x18002ebea  push    rsi
0x18002ebeb  push    rdi
0x18002ebec  push    r12
0x18002ebee  push    r13
0x18002ebf0  push    r14
0x18002ebf2  push    r15
0x18002ebf4  lea     rbp, [rsp-780h]
0x18002ebfc  sub     rsp, 880h
0x18002ec03  mov     rax, cs:__security_cookie
0x18002ec0a  xor     rax, rsp
0x18002ec0d  mov     [rbp+7B0h+var_40], rax
0x18002ec14  mov     rsi, r8
0x18002ec17  mov     rdi, rdx
0x18002ec1a  mov     [rsp+8B0h+var_850], rcx
0x18002ec1f  mov     r9d, 1; unsigned __int16
0x18002ec25  mov     r8d, 50Ch; unsigned __int16
0x18002ec2b  lea     rdx, aCdefragoperati_2; "CDefragOperation::_ReadDefragListFile"
0x18002ec32  lea     rcx, [rsp+8B0h+var_890]; this
0x18002ec37  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002ec3c  nop
0x18002ec3d  xor     r15d, r15d
0x18002ec40  mov     ebx, r15d
0x18002ec43  mov     [rsp+8B0h+var_858], rbx
0x18002ec48  mov     r14d, r15d
0x18002ec4b  mov     eax, 519h
0x18002ec50  test    rsi, rsi
0x18002ec53  jz      loc_18002EE85
0x18002ec59  mov     [rsp+8B0h+var_890], r15d
0x18002ec5e  mov     [rsp+8B0h+var_88C], ax
0x18002ec63  test    rdi, rdi
0x18002ec66  jz      short loc_18002EC78
0x18002ec68  mov     rax, [rdi]
0x18002ec6b  mov     rcx, rdi
0x18002ec6e  mov     rax, [rax+8]
0x18002ec72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec77  nop
0x18002ec78  mov     rbx, rdi
0x18002ec7b  mov     [rsp+8B0h+var_858], rbx
0x18002ec80  mov     rax, [rdi]
0x18002ec83  mov     rcx, rdi
0x18002ec86  mov     rax, [rax+160h]
0x18002ec8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec92  mov     [rsp+8B0h+var_890], eax
0x18002ec96  test    eax, eax
0x18002ec98  mov     eax, 51Dh
0x18002ec9d  js      loc_18002EE8D
0x18002eca3  mov     [rsp+8B0h+var_88C], ax
0x18002eca8  lea     rdx, aRtCcsUnicode; "rt, ccs=UNICODE"
0x18002ecaf  mov     rcx, rsi; FileName
0x18002ecb2  call    cs:__imp__wfopen
0x18002ecb8  mov     r13, rax
0x18002ecbb  mov     ecx, 521h
0x18002ecc0  test    rax, rax
0x18002ecc3  jz      loc_18002EE76
0x18002ecc9  mov     [rsp+8B0h+var_88C], cx
0x18002ecce  mov     ecx, 208h; Size
0x18002ecd3  call    cs:__imp_malloc
0x18002ecd9  mov     r14, rax
0x18002ecdc  test    rax, rax
0x18002ecdf  mov     eax, 524h
0x18002ece4  jz      loc_18002EE01
0x18002ecea  mov     esi, r15d
0x18002eced  mov     [rsp+8B0h+var_890], r15d
0x18002ecf2  mov     [rsp+8B0h+var_88C], ax
0x18002ecf7  mov     r12d, 104h
0x18002ecfd  mov     r8, r13; Stream
0x18002ed00  mov     edx, 400h; BufferCount
0x18002ed05  lea     rcx, [rsp+8B0h+Buffer]; Buffer
0x18002ed0a  call    cs:__imp_fgetws
0x18002ed10  test    rax, rax
0x18002ed13  jz      loc_18002EE19
0x18002ed19  lea     r15, [rsp+8B0h+Buffer]
0x18002ed1e  xor     edx, edx
0x18002ed20  cmp     [r15], dx
0x18002ed24  jz      loc_18002EDF4
0x18002ed2a  cmp     word ptr [r15], 0Ah
0x18002ed2f  jz      short loc_18002ED82
0x18002ed31  cmp     word ptr [r15], 0Dh
0x18002ed36  jz      loc_18002EDC6
0x18002ed3c  lea     eax, [r12-1]
0x18002ed41  cmp     esi, eax
0x18002ed43  jb      short loc_18002ED73
0x18002ed45  add     r12d, r12d
0x18002ed48  mov     edx, r12d
0x18002ed4b  add     rdx, rdx; Size
0x18002ed4e  mov     rcx, r14; Block
0x18002ed51  call    cs:__imp_realloc
0x18002ed57  xor     edx, edx
0x18002ed59  test    rax, rax
0x18002ed5c  jz      loc_18002EDFC
0x18002ed62  mov     [rsp+8B0h+var_890], edx
0x18002ed66  mov     ecx, 534h
0x18002ed6b  mov     [rsp+8B0h+var_88C], cx
0x18002ed70  mov     r14, rax
0x18002ed73  mov     ecx, esi
0x18002ed75  movzx   eax, word ptr [r15]
0x18002ed79  mov     [r14+rcx*2], ax
0x18002ed7e  inc     esi
0x18002ed80  jmp     short loc_18002EDC6
0x18002ed82  test    esi, esi
0x18002ed84  jz      short loc_18002EDC6
0x18002ed86  mov     ecx, esi
0x18002ed88  mov     [r14+rcx*2], dx
0x18002ed8d  mov     rax, [rdi]
0x18002ed90  mov     rdx, r14
0x18002ed93  mov     rcx, rdi
0x18002ed96  mov     rax, [rax+150h]
0x18002ed9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eda2  mov     [rsp+8B0h+var_890], eax
0x18002eda6  test    eax, eax
0x18002eda8  mov     eax, 542h
0x18002edad  js      short loc_18002EE09
0x18002edaf  mov     [rsp+8B0h+var_88C], ax
0x18002edb4  mov     r8d, r12d
0x18002edb7  add     r8, r8; Size
0x18002edba  xor     edx, edx; Val
0x18002edbc  mov     rcx, r14; void *
0x18002edbf  call    memset_0
0x18002edc4  xor     esi, esi
0x18002edc6  mov     rcx, [rsp+8B0h+var_850]
0x18002edcb  mov     rax, [rcx]
0x18002edce  mov     rax, [rax+20h]
0x18002edd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002edd7  mov     [rsp+8B0h+var_890], eax
0x18002eddb  xor     edx, edx
0x18002eddd  test    eax, eax
0x18002eddf  mov     eax, 549h
0x18002ede4  js      short loc_18002EE09
0x18002ede6  mov     [rsp+8B0h+var_88C], ax
0x18002edeb  add     r15, 2
0x18002edef  jmp     loc_18002ED20
0x18002edf4  xor     r15d, r15d
0x18002edf7  jmp     loc_18002ECFD
0x18002edfc  mov     eax, 534h
0x18002ee01  mov     [rsp+8B0h+var_890], 8007000Eh
0x18002ee09  mov     [rsp+8B0h+var_88A], ax
0x18002ee0e  mov     rcx, r13; Stream
0x18002ee11  call    cs:__imp_fclose
0x18002ee17  jmp     short loc_18002EE92
0x18002ee19  test    esi, esi
0x18002ee1b  jz      short loc_18002EE4B
0x18002ee1d  mov     ecx, esi
0x18002ee1f  mov     [r14+rcx*2], r15w
0x18002ee24  mov     rax, [rdi]
0x18002ee27  mov     rdx, r14
0x18002ee2a  mov     rcx, rdi
0x18002ee2d  mov     rax, [rax+150h]
0x18002ee34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee39  mov     [rsp+8B0h+var_890], eax
0x18002ee3d  test    eax, eax
0x18002ee3f  mov     eax, 551h
0x18002ee44  js      short loc_18002EE09
0x18002ee46  mov     [rsp+8B0h+var_88C], ax
0x18002ee4b  mov     rax, [rdi]
0x18002ee4e  mov     rcx, rdi
0x18002ee51  mov     rax, [rax+158h]
0x18002ee58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee5d  mov     [rsp+8B0h+var_890], eax
0x18002ee61  test    eax, eax
0x18002ee63  mov     eax, 554h
0x18002ee68  js      short loc_18002EE09
0x18002ee6a  mov     [rsp+8B0h+var_88C], ax
0x18002ee6f  mov     [rsp+8B0h+var_890], r15d
0x18002ee74  jmp     short loc_18002EE0E
0x18002ee76  mov     [rsp+8B0h+var_890], 89000030h
0x18002ee7e  mov     [rsp+8B0h+var_88A], cx
0x18002ee83  jmp     short loc_18002EE92
0x18002ee85  mov     [rsp+8B0h+var_890], 80070057h
0x18002ee8d  mov     [rsp+8B0h+var_88A], ax
0x18002ee92  mov     rcx, r14; Block
0x18002ee95  call    cs:__imp_free
0x18002ee9b  mov     edi, [rsp+8B0h+var_890]
0x18002ee9f  test    rbx, rbx
0x18002eea2  jz      short loc_18002EEB4
0x18002eea4  mov     rcx, [rbx]
0x18002eea7  mov     rax, [rcx+10h]
0x18002eeab  mov     rcx, rbx
0x18002eeae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eeb3  nop
0x18002eeb4  lea     rcx, [rsp+8B0h+var_890]; this
0x18002eeb9  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002eebe  mov     eax, edi
0x18002eec0  mov     rcx, [rbp+7B0h+var_40]
0x18002eec7  xor     rcx, rsp; StackCookie
0x18002eeca  call    __security_check_cookie
0x18002eecf  mov     rbx, [rsp+8B0h+arg_18]
0x18002eed7  add     rsp, 880h
0x18002eede  pop     r15
0x18002eee0  pop     r14
0x18002eee2  pop     r13
0x18002eee4  pop     r12
0x18002eee6  pop     rdi
0x18002eee7  pop     rsi
0x18002eee8  pop     rbp
0x18002eee9  retn
```
