# SString::LoadResourceAndReturnHR(CCompRC *,CCompRC::ResourceCategory,int)

- ea: `0x180040ce4`
- end: `0x180040e66`
- name: `?LoadResourceAndReturnHR@SString@@QEAAJPEAVCCompRC@@W4ResourceCategory@2@H@Z`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180040cc8`

## callees

- `0x180028f1c`
- `0x1800292d4`
- `0x180039f18`
- `0x18003a0bc`
- `0x18003a974`
- `0x18003efb0`
- `0x18003f898`
- `0x18003fd88`
- `0x180040ce4`

## pseudocode

```c
__int64 __fastcall SString::LoadResourceAndReturnHR(__int64 a1, __int64 a2, int a3, unsigned int a4)
{
  int v6; // esi
  struct CCompRC *DefaultResourceDll; // r14
  __int64 v8; // rdx
  char v9; // r14
  __int64 v10; // rax
  __int64 v11; // rdi
  __int64 v13; // [rsp+30h] [rbp-48h] BYREF
  BOOL v14; // [rsp+38h] [rbp-40h]
  __int64 v15; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v16[3]; // [rsp+48h] [rbp-30h] BYREF
  int v17; // [rsp+88h] [rbp+10h]
  int v18; // [rsp+90h] [rbp+18h] BYREF

  v18 = a3;
  v6 = -2147467259;
  DefaultResourceDll = CCompRC::GetDefaultResourceDll();
  if ( DefaultResourceDll )
  {
    try
    {
      try
      {
        v18 = 0;
        v13 = 0;
        if ( *(_DWORD *)a1 >> ((*(_DWORD *)(a1 + 8) & 1) == 0) == 1 )
          SString::Resize(a1, 255, 4, 0);
        while ( 1 )
        {
          v6 = CCompRC::LoadString(
                 DefaultResourceDll,
                 1,
                 a4,
                 *(_QWORD *)(a1 + 16),
                 *(_DWORD *)a1 >> ((*(_DWORD *)(a1 + 8) & 1) == 0),
                 &v18,
                 v13);
          if ( v6 < 0 )
          {
            SString::Clear((SString *)a1);
            goto LABEL_11;
          }
          if ( v18 < (*(_DWORD *)a1 >> ((*(_DWORD *)(a1 + 8) & 1) == 0)) - 1 )
            break;
          SString::Resize(a1, (unsigned int)(2 * v18), 4, 0);
        }
        SString::ConvertToIteratable((SString *)a1);
        SBuffer::EnsureMutable((SBuffer *)a1);
        v8 = *(_QWORD *)(a1 + 16);
        v9 = (*(_DWORD *)(a1 + 8) & 1) == 0;
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)(v8 + 2 * v10) );
        v11 = v8 + (int)((_DWORD)v10 << v9);
        SString::ConvertToIteratable((SString *)a1);
        SBuffer::EnsureMutable((SBuffer *)a1);
        SString::Resize(a1, (unsigned int)((v11 - *(_QWORD *)(a1 + 16)) >> v9), *(_DWORD *)(a1 + 8) & 7, 1);
LABEL_11:
        SString::ConvertToUnicode((SString *)a1);
        *(_DWORD *)(a1 + 8) |= 0x100u;
      }
      catch ( Exception *v15 )
      {
        v13 = v15;
        throw;
      }
    }
    catch ( ... )
    {
      v17 = IsCurrentExceptionSO();
      v14 = v13 != 0;
      v16[1] = 0;
      v16[0] = &DelegatingException::`vftable';
      v16[2] = -1;
      v18 = -2147467259;
      DelegatingException::~DelegatingException((DelegatingException *)v16);
      Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2>::~Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2>(&v13);
      if ( v17 )
        HandleStackOverflowAfterCatch();
      return (unsigned int)v18;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180040ce4  mov     rax, rsp
0x180040ce7  mov     [rax+8], rbx
0x180040ceb  mov     [rax+20h], rsi
0x180040cef  mov     [rax+18h], r8d
0x180040cf3  mov     [rax+10h], rdx
0x180040cf7  push    rdi
0x180040cf8  push    r14
0x180040cfa  push    r15
0x180040cfc  sub     rsp, 60h
0x180040d00  mov     r15d, r9d
0x180040d03  mov     rbx, rcx
0x180040d06  mov     esi, 80004005h
0x180040d0b  call    ?GetDefaultResourceDll@CCompRC@@SAPEAV1@XZ; CCompRC::GetDefaultResourceDll(void)
0x180040d10  mov     r14, rax
0x180040d13  xor     edi, edi
0x180040d15  test    rax, rax
0x180040d18  jz      loc_180040E4E
0x180040d1e  mov     [rsp+78h+arg_10], edi
0x180040d25  mov     [rsp+78h+var_48], rdi
0x180040d2a  mov     ecx, [rbx+8]
0x180040d2d  not     ecx
0x180040d2f  and     ecx, 1
0x180040d32  mov     eax, [rbx]
0x180040d34  shr     eax, cl
0x180040d36  cmp     eax, 1
0x180040d39  jnz     short loc_180040D4F
0x180040d3b  xor     r9d, r9d
0x180040d3e  mov     edx, 0FFh
0x180040d43  lea     r8d, [rdi+4]
0x180040d47  mov     rcx, rbx
0x180040d4a  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x180040d4f  mov     ecx, [rbx+8]
0x180040d52  not     ecx
0x180040d54  and     ecx, 1
0x180040d57  mov     eax, [rbx]
0x180040d59  shr     eax, cl
0x180040d5b  lea     rcx, [rsp+78h+arg_10]
0x180040d63  mov     [rsp+78h+var_50], rcx
0x180040d68  mov     [rsp+78h+var_58], eax
0x180040d6c  mov     r9, [rbx+10h]
0x180040d70  mov     r8d, r15d
0x180040d73  mov     edx, 1
0x180040d78  mov     rcx, r14
0x180040d7b  call    ?LoadString@CCompRC@@QEAAJW4ResourceCategory@1@IPEAGHPEAH@Z; CCompRC::LoadString(CCompRC::ResourceCategory,uint,ushort *,int,int *)
0x180040d80  mov     esi, eax
0x180040d82  test    eax, eax
0x180040d84  jns     short loc_180040D93
0x180040d86  mov     rcx, rbx; this
0x180040d89  call    ?Clear@SString@@QEAAXXZ; SString::Clear(void)
0x180040d8e  jmp     loc_180040E15
0x180040d93  mov     ecx, [rbx+8]
0x180040d96  not     ecx
0x180040d98  and     ecx, 1
0x180040d9b  mov     eax, [rbx]
0x180040d9d  shr     eax, cl
0x180040d9f  dec     eax
0x180040da1  mov     edx, [rsp+78h+arg_10]
0x180040da8  mov     rcx, rbx; this
0x180040dab  cmp     edx, eax
0x180040dad  jge     short loc_180040E24
0x180040daf  call    ?ConvertToIteratable@SString@@AEBAXXZ; SString::ConvertToIteratable(void)
0x180040db4  mov     rcx, rbx; this
0x180040db7  call    ?EnsureMutable@SBuffer@@IEBAXXZ; SBuffer::EnsureMutable(void)
0x180040dbc  mov     rdx, [rbx+10h]
0x180040dc0  mov     r14d, [rbx+8]
0x180040dc4  not     r14d
0x180040dc7  and     r14d, 1
0x180040dcb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180040dcf  inc     rax
0x180040dd2  cmp     [rdx+rax*2], di
0x180040dd6  jnz     short loc_180040DCF
0x180040dd8  mov     ecx, r14d
0x180040ddb  shl     eax, cl
0x180040ddd  movsxd  rdi, eax
0x180040de0  add     rdi, rdx
0x180040de3  mov     rcx, rbx; this
0x180040de6  call    ?ConvertToIteratable@SString@@AEBAXXZ; SString::ConvertToIteratable(void)
0x180040deb  mov     rcx, rbx; this
0x180040dee  call    ?EnsureMutable@SBuffer@@IEBAXXZ; SBuffer::EnsureMutable(void)
0x180040df3  mov     r8d, [rbx+8]
0x180040df7  and     r8d, 7
0x180040dfb  sub     rdi, [rbx+10h]
0x180040dff  mov     ecx, r14d
0x180040e02  sar     rdi, cl
0x180040e05  mov     r9d, 1
0x180040e0b  mov     edx, edi
0x180040e0d  mov     rcx, rbx
0x180040e10  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x180040e15  mov     rcx, rbx; this
0x180040e18  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180040e1d  bts     dword ptr [rbx+8], 8
0x180040e22  jmp     short loc_180040E4E
0x180040e24  add     edx, edx
0x180040e26  xor     r9d, r9d
0x180040e29  lea     r8d, [r9+4]
0x180040e2d  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x180040e32  jmp     loc_180040D4F
0x180040e37  xor     edi, edi
0x180040e39  cmp     [rsp+78h+arg_8], edi
0x180040e40  jz      short loc_180040E47
0x180040e42  call    ?HandleStackOverflowAfterCatch@@YAXXZ; HandleStackOverflowAfterCatch(void)
0x180040e47  mov     esi, [rsp+78h+arg_10]
0x180040e4e  mov     eax, esi
0x180040e50  lea     r11, [rsp+78h+var_18]
0x180040e55  mov     rbx, [r11+20h]
0x180040e59  mov     rsi, [r11+38h]
0x180040e5d  mov     rsp, r11
0x180040e60  pop     r15
0x180040e62  pop     r14
0x180040e64  pop     rdi
0x180040e65  retn
```
