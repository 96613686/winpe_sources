# SwitchedRtlGetVersion

- ea: `0x180001ed0`
- end: `0x180002115`
- name: `SwitchedRtlGetVersion`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180001a50`

## callees

- `0x180001ed0`
- `0x180002120`
- `0x180002c20`
- `0x180002c60`
- `0x1800cc810`
- `0x18012d320`
- `0x1801616d0`
- `0x18016f020`

## string_xrefs

- `0x180001ff7`: `TerminalServices-RemoteConnectionManager-AllowAppServerMode`

## pseudocode

```c
__int64 __fastcall SwitchedRtlGetVersion(int *a1)
{
  struct _PEB *v2; // rdi
  __int64 (*v3)(void); // rax
  int v4; // eax
  wchar_t *Buffer; // r8
  int v6; // esi
  size_t v7; // rax
  __int128 v9; // [rsp+30h] [rbp-38h] BYREF
  int v10; // [rsp+70h] [rbp+8h] BYREF
  int v11; // [rsp+78h] [rbp+10h] BYREF
  int v12; // [rsp+80h] [rbp+18h] BYREF
  int v13; // [rsp+88h] [rbp+20h] BYREF

  v9 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v2 = NtCurrentPeb();
  v10 = 0;
  a1[1] = v2->OSMajorVersion;
  a1[2] = v2->OSMinorVersion;
  a1[3] = v2->OSBuildNumber;
  a1[4] = v2->OSPlatformId;
  v3 = (__int64 (*)(void))qword_1801C67C8;
  if ( qword_1801C67C8
    || (v3 = (__int64 (*)(void))SbSelectProcedure(2880154539LL, 0, "kLsE", 0), (qword_1801C67C8 = (__int64)v3) != 0) )
  {
    v4 = v3() - 1;
    if ( v4 )
    {
      if ( v4 == 1 )
      {
        a1[2] = 3;
        a1[3] = 9600;
        a1[1] = 6;
      }
    }
    else
    {
      a1[2] = 2;
      a1[3] = 9200;
      a1[1] = 6;
    }
  }
  Buffer = v2->CSDVersion.Buffer;
  if ( !Buffer || !*Buffer || (int)RtlStringCbCopyW(a1 + 5, 256) < 0 )
    *((_WORD *)a1 + 10) = 0;
  v6 = *a1;
  if ( ((*a1 - 284) & 0xFFFFFFF7) == 0 )
  {
    *((_WORD *)a1 + 138) = HIBYTE(v2->OSCSDVersion);
    *((_WORD *)a1 + 139) = (unsigned __int8)v2->OSCSDVersion;
    *((_WORD *)a1 + 140) = RtlGetSuiteMask();
    if ( v6 == 292 )
      a1[71] = RtlGetSuiteMask() & 0x1FFFF;
    *((_BYTE *)a1 + 282) = 0;
    if ( (unsigned __int8)RtlGetNtProductType(&v10) )
      *((_BYTE *)a1 + 282) = v10;
    *(_QWORD *)&v9 = 0;
    *((_QWORD *)&v9 + 1) = L"TerminalServices-RemoteConnectionManager-AllowAppServerMode";
    v7 = 2 * wcslen(L"TerminalServices-RemoteConnectionManager-AllowAppServerMode");
    if ( v7 >= 0xFFFE )
      LOWORD(v7) = -4;
    LOWORD(v9) = v7;
    WORD1(v9) = v7 + 2;
    if ( (int)ZwQueryLicenseValue(&v9, &v11, &v13, 4, &v12) < 0 || v13 != 1 || v11 != 4 || v12 != 4 )
    {
      *((_WORD *)a1 + 140) &= ~0x10u;
      *((_WORD *)a1 + 140) |= 0x100u;
      if ( *a1 == 292 )
      {
        a1[71] &= 0xFFFDFFEF;
        a1[71] |= 0x100u;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180001ed0  mov     rax, rsp
0x180001ed3  push    rbx
0x180001ed4  push    rbp
0x180001ed5  push    rsi
0x180001ed6  push    rdi
0x180001ed7  push    r14
0x180001ed9  sub     rsp, 40h
0x180001edd  xor     ebp, ebp
0x180001edf  xorps   xmm0, xmm0
0x180001ee2  movups  xmmword ptr [rax-38h], xmm0
0x180001ee6  mov     [rax+10h], ebp
0x180001ee9  mov     rbx, rcx
0x180001eec  mov     [rax+18h], ebp
0x180001eef  mov     [rax+20h], ebp
0x180001ef2  mov     rdi, gs:60h
0x180001efb  mov     [rax+8], ebp
0x180001efe  mov     eax, [rdi+118h]
0x180001f04  mov     [rcx+4], eax
0x180001f07  mov     eax, [rdi+11Ch]
0x180001f0d  mov     [rcx+8], eax
0x180001f10  movzx   eax, word ptr [rdi+120h]
0x180001f17  mov     [rcx+0Ch], eax
0x180001f1a  mov     eax, [rdi+124h]
0x180001f20  mov     [rcx+10h], eax
0x180001f23  mov     rax, cs:qword_1801C67C8
0x180001f2a  test    rax, rax
0x180001f2d  jnz     short loc_180001F51
0x180001f2f  xor     r9d, r9d
0x180001f32  lea     r8, g_SbModuleTable_RTL; "kLsE"
0x180001f39  xor     edx, edx
0x180001f3b  mov     ecx, 0ABABABABh
0x180001f40  call    SbSelectProcedure
0x180001f45  mov     cs:qword_1801C67C8, rax
0x180001f4c  test    rax, rax
0x180001f4f  jz      short loc_180001F68
0x180001f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f56  sub     eax, 1
0x180001f59  jz      loc_1800020A0
0x180001f5f  cmp     eax, 1
0x180001f62  jz      loc_1800020BA
0x180001f68  mov     r8, [rdi+2F0h]
0x180001f6f  mov     r14d, 100h
0x180001f75  test    r8, r8
0x180001f78  jz      short loc_180001F84
0x180001f7a  cmp     [r8], bp
0x180001f7e  jnz     loc_1800020E7
0x180001f84  mov     [rbx+14h], bp
0x180001f88  mov     esi, [rbx]
0x180001f8a  lea     eax, [rsi-11Ch]
0x180001f90  test    eax, 0FFFFFFF7h
0x180001f95  jnz     loc_18000207F
0x180001f9b  movzx   eax, byte ptr [rdi+123h]
0x180001fa2  mov     ecx, 0FFh
0x180001fa7  mov     [rbx+114h], ax
0x180001fae  movzx   eax, word ptr [rdi+122h]
0x180001fb5  and     ax, cx
0x180001fb8  mov     [rbx+116h], ax
0x180001fbf  call    RtlGetSuiteMask
0x180001fc4  mov     [rbx+118h], ax
0x180001fcb  cmp     esi, 124h
0x180001fd1  jz      loc_180002100
0x180001fd7  lea     rcx, [rsp+68h+arg_0]
0x180001fdc  mov     [rbx+11Ah], bpl
0x180001fe3  call    RtlGetNtProductType
0x180001fe8  test    al, al
0x180001fea  jz      short loc_180001FF7
0x180001fec  movzx   eax, byte ptr [rsp+68h+arg_0]
0x180001ff1  mov     [rbx+11Ah], al
0x180001ff7  lea     rcx, aTerminalservic; "TerminalServices-RemoteConnectionManage"...
0x180001ffe  mov     [rsp+68h+var_38], rbp
0x180002003  mov     [rsp+68h+var_30], rcx
0x180002008  call    wcslen
0x18000200d  add     rax, rax
0x180002010  cmp     rax, 0FFFEh
0x180002016  jb      short loc_18000201D
0x180002018  mov     eax, 0FFFCh
0x18000201d  mov     word ptr [rsp+68h+var_38], ax
0x180002022  lea     r8, [rsp+68h+arg_18]
0x18000202a  add     ax, 2
0x18000202e  lea     rdx, [rsp+68h+arg_8]
0x180002033  mov     word ptr [rsp+68h+var_38+2], ax
0x180002038  lea     rcx, [rsp+68h+var_38]
0x18000203d  lea     rax, [rsp+68h+arg_10]
0x180002045  mov     r9d, 4
0x18000204b  mov     [rsp+68h+var_48], rax
0x180002050  call    ZwQueryLicenseValue
0x180002055  test    eax, eax
0x180002057  js      short loc_180002063
0x180002059  cmp     [rsp+68h+arg_18], 1
0x180002061  jz      short loc_18000208D
0x180002063  mov     eax, 0FFEFh
0x180002068  and     [rbx+118h], ax
0x18000206f  or      [rbx+118h], r14w
0x180002077  cmp     dword ptr [rbx], 124h
0x18000207d  jz      short loc_1800020D4
0x18000207f  xor     eax, eax
0x180002081  add     rsp, 40h
0x180002085  pop     r14
0x180002087  pop     rdi
0x180002088  pop     rsi
0x180002089  pop     rbp
0x18000208a  pop     rbx
0x18000208b  retn
0x18000208d  cmp     [rsp+68h+arg_8], 4
0x180002092  jnz     short loc_180002063
0x180002094  cmp     [rsp+68h+arg_10], 4
0x18000209c  jz      short loc_18000207F
0x18000209e  jmp     short loc_180002063
0x1800020a0  mov     dword ptr [rbx+8], 2
0x1800020a7  mov     dword ptr [rbx+0Ch], 23F0h
0x1800020ae  mov     dword ptr [rbx+4], 6
0x1800020b5  jmp     loc_180001F68
0x1800020ba  mov     dword ptr [rbx+8], 3
0x1800020c1  mov     dword ptr [rbx+0Ch], 2580h
0x1800020c8  mov     dword ptr [rbx+4], 6
0x1800020cf  jmp     loc_180001F68
0x1800020d4  and     dword ptr [rbx+11Ch], 0FFFDFFEFh
0x1800020de  or      [rbx+11Ch], r14d
0x1800020e5  jmp     short loc_18000207F
0x1800020e7  mov     rdx, r14
0x1800020ea  lea     rcx, [rbx+14h]
0x1800020ee  call    RtlStringCbCopyW
0x1800020f3  test    eax, eax
0x1800020f5  jns     loc_180001F88
0x1800020fb  jmp     loc_180001F84
0x180002100  call    RtlGetSuiteMask
0x180002105  and     eax, 1FFFFh
0x18000210a  mov     [rbx+11Ch], eax
0x180002110  jmp     loc_180001FD7
```
