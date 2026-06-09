# CASFOutput::SetMediaType(CMediaType const *)

- ea: `0x18000ce10`
- end: `0x18000cf8a`
- name: `?SetMediaType@CASFOutput@@UEAAJPEBVCMediaType@@@Z`
- size: `378`
- prototype: `int(CASFOutput *__hidden this, const struct CMediaType *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180001460`
- `0x18000724c`
- `0x18000ce10`
- `0x180016314`
- `0x18001f010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000cf02`
- `ole32!CoTaskMemFree` at `0x18000cf02`

## pseudocode

```c
__int64 __fastcall CASFOutput::SetMediaType(CASFOutput *this, const struct CMediaType *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  struct _AMMediaType *v6; // rbp
  int v7; // esi
  struct _AMMediaType *v8; // rax
  const struct CMediaType *v9; // rdx
  __int64 v11; // [rsp+20h] [rbp-28h] BYREF

  v4 = *((_QWORD *)this + 37);
  if ( *(_DWORD *)(v4 + 448) )
  {
    v5 = *((unsigned int *)this + 76);
    v11 = 0;
    v6 = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**(_QWORD **)(v4 + 344) + 48LL))(
           *(_QWORD *)(v4 + 344),
           v5,
           &v11);
    if ( v7 < 0 )
      goto LABEL_12;
    if ( *(_QWORD *)&FORMAT_VideoInfo2.Data1 == *(_QWORD *)((char *)a2 + 44)
      && *(_QWORD *)FORMAT_VideoInfo2.Data4 == *(_QWORD *)((char *)a2 + 52) )
    {
      v8 = ConstructVIH1Type((const struct _AMMediaType *)a2);
      v6 = v8;
      if ( !v8 )
      {
        v7 = -2147024882;
LABEL_12:
        CoTaskMemFree(v6);
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        return (unsigned int)v7;
      }
      v9 = (const struct CMediaType *)v8;
    }
    else
    {
      v9 = a2;
    }
    v7 = (*(__int64 (__fastcall **)(__int64, const struct CMediaType *))(*(_QWORD *)v11 + 40LL))(v11, v9);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)(*((_QWORD *)this + 37) + 344LL) + 56LL))(
             *(_QWORD *)(*((_QWORD *)this + 37) + 344LL),
             *((unsigned int *)this + 76),
             v11);
      if ( v7 >= 0 )
        CMediaType::Set((struct _AMMediaType *)((char *)this + 104), (const struct _AMMediaType *)a2);
    }
    goto LABEL_12;
  }
  v7 = 0;
  *((_DWORD *)this + 83) = *(_QWORD *)&FORMAT_VideoInfo.Data1 == *(_QWORD *)((char *)a2 + 44)
                        && *(_QWORD *)FORMAT_VideoInfo.Data4 == *(_QWORD *)((char *)a2 + 52)
                        && *(_QWORD *)&FORMAT_VideoInfo2.Data1 == *(_QWORD *)((char *)this + 148)
                        && *(_QWORD *)FORMAT_VideoInfo2.Data4 == *(_QWORD *)((char *)this + 156);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000ce10  mov     [rsp+arg_10], rbx
0x18000ce15  push    rbp
0x18000ce16  push    rsi
0x18000ce17  push    rdi
0x18000ce18  sub     rsp, 30h
0x18000ce1c  mov     rax, cs:__security_cookie
0x18000ce23  xor     rax, rsp
0x18000ce26  mov     [rsp+48h+var_20], rax
0x18000ce2b  mov     rbx, rcx
0x18000ce2e  mov     rdi, rdx
0x18000ce31  mov     rcx, [rcx+128h]
0x18000ce38  cmp     dword ptr [rcx+1C0h], 0
0x18000ce3f  jz      loc_18000CF20
0x18000ce45  mov     edx, [rbx+130h]
0x18000ce4b  lea     r8, [rsp+48h+var_28]
0x18000ce50  mov     [rsp+48h+var_28], 0
0x18000ce59  xor     ebp, ebp
0x18000ce5b  mov     rcx, [rcx+158h]
0x18000ce62  mov     rax, [rcx]
0x18000ce65  mov     rax, [rax+30h]
0x18000ce69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce6e  mov     esi, eax
0x18000ce70  test    eax, eax
0x18000ce72  js      loc_18000CEFF
0x18000ce78  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x18000ce7f  cmp     rax, [rdi+2Ch]
0x18000ce83  jnz     short loc_18000CEAE
0x18000ce85  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x18000ce8c  cmp     rax, [rdi+34h]
0x18000ce90  jnz     short loc_18000CEAE
0x18000ce92  mov     rcx, rdi; struct _AMMediaType *
0x18000ce95  call    ?ConstructVIH1Type@@YAPEAU_AMMediaType@@PEBU1@@Z; ConstructVIH1Type(_AMMediaType const *)
0x18000ce9a  mov     rbp, rax
0x18000ce9d  test    rax, rax
0x18000cea0  jnz     short loc_18000CEA9
0x18000cea2  mov     esi, 8007000Eh
0x18000cea7  jmp     short loc_18000CEFF
0x18000cea9  mov     rdx, rbp
0x18000ceac  jmp     short loc_18000CEB1
0x18000ceae  mov     rdx, rdi
0x18000ceb1  mov     rcx, [rsp+48h+var_28]
0x18000ceb6  mov     rax, [rcx]
0x18000ceb9  mov     rax, [rax+28h]
0x18000cebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cec2  mov     esi, eax
0x18000cec4  test    eax, eax
0x18000cec6  js      short loc_18000CEFF
0x18000cec8  mov     rax, [rbx+128h]
0x18000cecf  mov     r8, [rsp+48h+var_28]
0x18000ced4  mov     edx, [rbx+130h]
0x18000ceda  mov     rcx, [rax+158h]
0x18000cee1  mov     rax, [rcx]
0x18000cee4  mov     rax, [rax+38h]
0x18000cee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ceed  mov     esi, eax
0x18000ceef  test    eax, eax
0x18000cef1  js      short loc_18000CEFF
0x18000cef3  lea     rcx, [rbx+68h]; this
0x18000cef7  mov     rdx, rdi; struct _AMMediaType *
0x18000cefa  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
0x18000ceff  mov     rcx, rbp; pv
0x18000cf02  call    cs:__imp_CoTaskMemFree
0x18000cf08  mov     rcx, [rsp+48h+var_28]
0x18000cf0d  test    rcx, rcx
0x18000cf10  jz      short loc_18000CF6E
0x18000cf12  mov     rax, [rcx]
0x18000cf15  mov     rax, [rax+10h]
0x18000cf19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf1e  jmp     short loc_18000CF6E
0x18000cf20  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x18000cf27  xor     esi, esi
0x18000cf29  cmp     rax, [rdx+2Ch]
0x18000cf2d  jnz     short loc_18000CF68
0x18000cf2f  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x18000cf36  cmp     rax, [rdx+34h]
0x18000cf3a  jnz     short loc_18000CF68
0x18000cf3c  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x18000cf43  cmp     rax, [rbx+94h]
0x18000cf4a  jnz     short loc_18000CF68
0x18000cf4c  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x18000cf53  cmp     rax, [rbx+9Ch]
0x18000cf5a  jnz     short loc_18000CF68
0x18000cf5c  mov     dword ptr [rbx+14Ch], 1
0x18000cf66  jmp     short loc_18000CF6E
0x18000cf68  mov     [rbx+14Ch], esi
0x18000cf6e  mov     eax, esi
0x18000cf70  mov     rcx, [rsp+48h+var_20]
0x18000cf75  xor     rcx, rsp; StackCookie
0x18000cf78  call    __security_check_cookie
0x18000cf7d  mov     rbx, [rsp+48h+arg_10]
0x18000cf82  add     rsp, 30h
0x18000cf86  pop     rdi
0x18000cf87  pop     rsi
0x18000cf88  pop     rbp
0x18000cf89  retn
```
