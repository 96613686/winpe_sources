# LOCATOR::FReadDebugDirInfo(void)

- ea: `0x180087230`
- end: `0x1800873ee`
- name: `?FReadDebugDirInfo@LOCATOR@@AEAA_NXZ`
- size: `446`
- prototype: `bool __fastcall(LOCATOR *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180084420`
- `0x180086180`

## callees

- `0x180085130`
- `0x180087230`
- `0x1801d6350`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18008733f`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18008733f`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180087325`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180087325`

## pseudocode

```c
bool __fastcall LOCATOR::FReadDebugDirInfo(LOCATOR *this)
{
  int (__fastcall *v1)(_QWORD, char *, _QWORD); // rax
  size_t v3; // rbp
  int (__fastcall *v4)(_QWORD, char *, _DWORD *); // rax
  bool result; // al
  FILE **v6; // r14
  FILE *v7; // r14
  bool v8; // al
  __int64 (__fastcall *v9)(_QWORD, _QWORD, _QWORD, _DWORD *); // rax
  int v10; // eax
  __int64 (__fastcall *v11)(_QWORD, __int64, _QWORD, _DWORD *); // rax
  __int64 v12; // rdx
  _DWORD Buffer[204]; // [rsp+30h] [rbp-358h] BYREF

  v1 = (int (__fastcall *)(_QWORD, char *, _QWORD))*((_QWORD *)this + 269);
  if ( v1 && v1(*((_QWORD *)this + 257), (char *)this + 3356, 0) < 0 )
    goto LABEL_7;
  v3 = *((unsigned int *)this + 839);
  if ( !(_DWORD)v3 )
    goto LABEL_7;
  if ( (unsigned int)v3 > 0x324 )
    goto LABEL_24;
  v4 = (int (__fastcall *)(_QWORD, char *, _DWORD *))*((_QWORD *)this + 269);
  if ( v4 )
  {
    if ( v4(*((_QWORD *)this + 257), (char *)this + 3356, Buffer) < 0 )
    {
LABEL_7:
      *(_DWORD *)this = 19;
LABEL_8:
      result = 0;
      *((_WORD *)this + 2) = 0;
      return result;
    }
  }
  else
  {
    v6 = (FILE **)((char *)this + 2264);
    if ( !*((_BYTE *)this + 3352) )
      v6 = (FILE **)((char *)this + 3336);
    v7 = *v6;
    if ( v7 )
    {
      if ( fseek(v7, *((_DWORD *)this + 841), 0) )
        goto LABEL_7;
      v8 = fread(Buffer, 1u, v3, v7) == v3;
    }
    else
    {
      v9 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _DWORD *))*((_QWORD *)this + 267);
      if ( v9 )
      {
        v10 = v9(*((_QWORD *)this + 257), *((unsigned int *)this + 841), (unsigned int)v3, Buffer);
      }
      else
      {
        v11 = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _DWORD *))*((_QWORD *)this + 268);
        if ( !v11 )
          goto LABEL_7;
        v12 = *((unsigned int *)this + 840);
        if ( !(_DWORD)v12 )
          goto LABEL_7;
        v10 = v11(*((_QWORD *)this + 257), v12, (unsigned int)v3, Buffer);
      }
      v8 = v10 >= 0;
    }
    if ( !v8 )
      goto LABEL_7;
  }
  if ( Buffer[0] != 808534606 && Buffer[0] != 1396986706 )
  {
LABEL_24:
    *(_DWORD *)this = 22;
    goto LABEL_8;
  }
  return LOCATOR::FDecodeCvData(this, Buffer, *((unsigned int *)this + 839));
}

```

## disassembly

```asm
0x180087230  mov     [rsp+arg_8], rbx
0x180087235  mov     [rsp+arg_10], rbp
0x18008723a  push    rsi
0x18008723b  push    rdi
0x18008723c  push    r14
0x18008723e  sub     rsp, 370h
0x180087245  mov     rax, cs:__security_cookie
0x18008724c  xor     rax, rsp
0x18008724f  mov     [rsp+388h+var_28], rax
0x180087257  mov     rax, [rcx+868h]
0x18008725e  mov     rdi, rcx
0x180087261  test    rax, rax
0x180087264  jz      short loc_180087281
0x180087266  lea     rdx, [rcx+0D1Ch]
0x18008726d  xor     r8d, r8d
0x180087270  mov     rcx, [rcx+808h]
0x180087277  call    cs:__guard_dispatch_icall_fptr
0x18008727d  test    eax, eax
0x18008727f  js      short loc_1800872C4
0x180087281  mov     ebp, [rdi+0D1Ch]
0x180087287  test    ebp, ebp
0x180087289  jz      short loc_1800872C4
0x18008728b  cmp     ebp, 324h
0x180087291  ja      loc_1800873E3
0x180087297  mov     rax, [rdi+868h]
0x18008729e  test    rax, rax
0x1800872a1  jz      short loc_1800872F8
0x1800872a3  mov     rcx, [rdi+808h]
0x1800872aa  lea     r8, [rsp+388h+Buffer]
0x1800872af  lea     rdx, [rdi+0D1Ch]
0x1800872b6  call    cs:__guard_dispatch_icall_fptr
0x1800872bc  test    eax, eax
0x1800872be  jns     loc_1800873B3
0x1800872c4  mov     dword ptr [rdi], 13h
0x1800872ca  xor     eax, eax
0x1800872cc  mov     [rdi+4], ax
0x1800872d0  mov     rcx, [rsp+388h+var_28]
0x1800872d8  xor     rcx, rsp; StackCookie
0x1800872db  call    __security_check_cookie
0x1800872e0  lea     r11, [rsp+388h+var_18]
0x1800872e8  mov     rbx, [r11+28h]
0x1800872ec  mov     rbp, [r11+30h]
0x1800872f0  mov     rsp, r11
0x1800872f3  pop     r14
0x1800872f5  pop     rdi
0x1800872f6  pop     rsi
0x1800872f7  retn
0x1800872f8  cmp     byte ptr [rdi+0D18h], 0
0x1800872ff  lea     r14, [rdi+8D8h]
0x180087306  jnz     short loc_18008730F
0x180087308  lea     r14, [rdi+0D08h]
0x18008730f  mov     r14, [r14]
0x180087312  mov     ecx, [rdi+0D24h]
0x180087318  test    r14, r14
0x18008731b  jz      short loc_18008734D
0x18008731d  mov     edx, ecx; Offset
0x18008731f  xor     r8d, r8d; Origin
0x180087322  mov     rcx, r14; Stream
0x180087325  call    cs:__imp_fseek
0x18008732b  test    eax, eax
0x18008732d  jnz     short loc_1800872C4
0x18008732f  mov     r9, r14; Stream
0x180087332  lea     rcx, [rsp+388h+Buffer]; Buffer
0x180087337  mov     r8, rbp; ElementCount
0x18008733a  mov     edx, 1; ElementSize
0x18008733f  call    cs:__imp_fread
0x180087345  cmp     rax, rbp
0x180087348  setz    al
0x18008734b  jmp     short loc_1800873AB
0x18008734d  mov     rax, [rdi+858h]
0x180087354  test    rax, rax
0x180087357  jz      short loc_180087373
0x180087359  mov     rdx, rcx
0x18008735c  lea     r9, [rsp+388h+Buffer]
0x180087361  mov     rcx, [rdi+808h]
0x180087368  mov     r8d, ebp
0x18008736b  call    cs:__guard_dispatch_icall_fptr
0x180087371  jmp     short loc_1800873A6
0x180087373  mov     rax, [rdi+860h]
0x18008737a  test    rax, rax
0x18008737d  jz      loc_1800872C4
0x180087383  mov     edx, [rdi+0D20h]
0x180087389  test    edx, edx
0x18008738b  jz      loc_1800872C4
0x180087391  mov     rcx, [rdi+808h]
0x180087398  lea     r9, [rsp+388h+Buffer]
0x18008739d  mov     r8d, ebp
0x1800873a0  call    cs:__guard_dispatch_icall_fptr
0x1800873a6  shr     eax, 1Fh
0x1800873a9  xor     al, 1
0x1800873ab  test    al, al
0x1800873ad  jz      loc_1800872C4
0x1800873b3  mov     eax, [rsp+388h+Buffer]
0x1800873b7  cmp     eax, 3031424Eh
0x1800873bc  jz      short loc_1800873C5
0x1800873be  cmp     eax, 53445352h
0x1800873c3  jnz     short loc_1800873E3
0x1800873c5  mov     r8d, [rdi+0D1Ch]; unsigned __int64
0x1800873cc  lea     rdx, [rsp+388h+Buffer]; void *
0x1800873d1  mov     rcx, rdi; this
0x1800873d4  call    ?FDecodeCvData@LOCATOR@@AEAA_NPEBX_K@Z; LOCATOR::FDecodeCvData(void const *,unsigned __int64)
0x1800873d9  test    al, al
0x1800873db  setnz   al
0x1800873de  jmp     loc_1800872D0
0x1800873e3  mov     dword ptr [rdi], 16h
0x1800873e9  jmp     loc_1800872CA
```
