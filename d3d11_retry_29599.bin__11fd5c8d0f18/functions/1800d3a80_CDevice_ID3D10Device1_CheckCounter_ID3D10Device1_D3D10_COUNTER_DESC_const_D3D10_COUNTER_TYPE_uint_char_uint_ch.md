# CDevice::ID3D10Device1_CheckCounter_(ID3D10Device1 *,D3D10_COUNTER_DESC const *,D3D10_COUNTER_TYPE *,uint *,char *,uint *,char *,uint *,char *,uint *)

- ea: `0x1800d3a80`
- end: `0x1800d3e47`
- name: `?ID3D10Device1_CheckCounter_@CDevice@@SAJPEAUID3D10Device1@@PEBUD3D10_COUNTER_DESC@@PEAW4D3D10_COUNTER_TYPE@@PEAIPEAD34343@Z`
- size: `967`
- prototype: `static int(struct ID3D10Device1 *, const struct D3D10_COUNTER_DESC *, enum D3D10_COUNTER_TYPE *, unsigned int *, char *, unsigned int *, char *, unsigned int *, char *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180022400`
- `0x18006893c`
- `0x1800782a0`
- `0x1800d3a80`

## string_xrefs

- `0x1800d3cde`: `A well-known counter to estimate the fractional amount of texture memory requests that weresatisfied by a cache, instead of going further out to video memory.`
- `0x1800d3cfc`: `A well-known counter to estimate the fractional amount of post vertex-shader vertex requests that weresatisfied by a cache, instead of running the vertex shader again.`
- `0x1800d3cd2`: `Texture Cache Hit Rate`
- `0x1800d3d18`: `A well-known counter to estimate the fractional amount of time the pixel shader was working oncomputation.`
- `0x1800d3cf0`: `Post Vertex-Shader Vertex Cache Hit Rate`
- `0x1800d3d31`: `A well-known counter to estimate the fractional amount of time the pixel shader was working onmemory accesses.`
- `0x1800d3d0c`: `Pixel Shader Computation Limited`
- `0x1800d3d4a`: `A well-known counter to estimate the fractional amount of time the geometry shader was working oncomputation.`
- `0x1800d3d63`: `A well-known counter to estimate the fractional amount of time the geometry shader was working onmemory accesses.`
- `0x1800d3d3e`: `Geometry Shader Computation Limited`
- `0x1800d3d7b`: `A well-known counter to estimate the fractional amount of time the vertex shader was working oncomputation.`
- `0x1800d3d94`: `A well-known counter to estimate the fractional amount of time the vertex shader was working onmemory accesses.`
- `0x1800d3d6f`: `Vertex Shader Computation Limited`
- `0x1800d3c93`: `A well-known counter to estimate the fractional amount of fill rate throughput utilized.`
- `0x1800d3b9a`: `A well-known counter to estimate the fractional amount of triangle setup throughput utilized.`
- `0x1800d3bb6`: `A well-known counter to estimate the fractional amount of vertex throughput utilized.`
- `0x1800d3bd2`: `A well-known counter to estimate the fractional amount of local video memory bandwidth utilized.`
- `0x1800d3bee`: `A well-known counter to estimate the fractional amount of host adapter bandwidth utilized.`
- `0x1800d3c06`: `A well-known counter to estimate the fractional amount of time for which the GPU was workingon other processing, not directly related to vertex, geometry, or pixel processing.`
- `0x1800d3c24`: `A well-known counter to estimate the fractional amount of time for which the GPU was workingon pixel processing.`
- `0x1800d3c40`: `A well-known counter to estimate the fractional amount of time for which the GPU was workingon geometry processing.`
- `0x1800d3c57`: `A well-known counter to estimate the fractional amount of time for which the GPU was workingon vertex processing.`
- `0x1800d3c75`: `A well-known counter to estimate the fractional amount of time for which the GPU was idle.`

## pseudocode

```c
__int64 __fastcall CDevice::ID3D10Device1_CheckCounter_(
        struct ID3D10Device1 *a1,
        const struct D3D11_COUNTER_DESC *a2,
        enum D3D11_COUNTER_TYPE *a3,
        unsigned int *a4,
        char *pszDest,
        unsigned int *a6,
        char *a7,
        unsigned int *a8,
        char *a9,
        unsigned int *a10)
{
  __int64 result; // rax
  unsigned int v15; // ebx
  D3D10_COUNTER Counter; // ecx
  __int32 v17; // ecx
  __int32 v18; // ecx
  __int32 v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  const char *v23; // r8
  const char *v24; // r11
  unsigned int v25; // r10d
  __int32 v26; // ecx
  __int32 v27; // ecx
  __int32 v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  _com_error *v32; // [rsp+50h] [rbp-48h] BYREF

  try
  {
    if ( !a2 || !a3 || a2->MiscFlags )
      ThrowFailure(-2147024809);
    if ( a2->Counter < 0 )
      return 2147942487LL;
    if ( a2->Counter >= D3D11_COUNTER_DEVICE_DEPENDENT_0 )
      return CDevice::CheckCounter((CDevice *)&a1[-31], a2, a3, a4, pszDest, a6, a7, a8, a9, a10);
    v15 = 18;
    if ( a2->Counter >= 18 )
      ThrowFailure(-2147024809);
    Counter = a2->Counter;
    if ( a2->Counter > 9 )
    {
      v26 = Counter - 10;
      if ( !v26 )
      {
        v23 = "Vertex Shader Memory Limited";
        v15 = 29;
        v24 = "A well-known counter to estimate the fractional amount of time the vertex shader was working onmemory accesses.";
        v25 = 112;
        goto LABEL_49;
      }
      v27 = v26 - 1;
      if ( !v27 )
      {
        v23 = "Vertex Shader Computation Limited";
        v15 = 34;
        v24 = "A well-known counter to estimate the fractional amount of time the vertex shader was working oncomputation.";
        v25 = 108;
        goto LABEL_49;
      }
      v28 = v27 - 1;
      if ( v28 )
      {
        v29 = v28 - 1;
        if ( v29 )
        {
          v30 = v29 - 1;
          if ( v30 )
          {
            v31 = v30 - 1;
            if ( v31 )
            {
              if ( v31 == 1 )
              {
                v23 = "Post Vertex-Shader Vertex Cache Hit Rate";
                v15 = 41;
                v24 = "A well-known counter to estimate the fractional amount of post vertex-shader vertex requests that "
                      "weresatisfied by a cache, instead of running the vertex shader again.";
                v25 = 168;
              }
              else
              {
                v23 = "Texture Cache Hit Rate";
                v15 = 23;
                v24 = "A well-known counter to estimate the fractional amount of texture memory requests that weresatisfi"
                      "ed by a cache, instead of going further out to video memory.";
                v25 = 159;
              }
            }
            else
            {
              v23 = "Pixel Shader Computation Limited";
              v15 = 33;
              v24 = "A well-known counter to estimate the fractional amount of time the pixel shader was working oncomputation.";
              v25 = 107;
            }
          }
          else
          {
            v23 = "Pixel Shader Memory Limited";
            v15 = 28;
            v24 = "A well-known counter to estimate the fractional amount of time the pixel shader was working onmemory accesses.";
            v25 = 111;
          }
        }
        else
        {
          v23 = "Geometry Shader Computation Limited";
          v15 = 36;
          v24 = "A well-known counter to estimate the fractional amount of time the geometry shader was working oncomputation.";
          v25 = 110;
        }
        goto LABEL_49;
      }
      v23 = "Geometry Shader Memory Limited";
      v15 = 31;
      v24 = "A well-known counter to estimate the fractional amount of time the geometry shader was working onmemory accesses.";
    }
    else
    {
      if ( Counter == D3D10_COUNTER_FILLRATE_THROUGHPUT_UTILIZATION )
      {
        v23 = "Fill Rate Utilization";
        v15 = 22;
        v24 = "A well-known counter to estimate the fractional amount of fill rate throughput utilized.";
        v25 = 89;
        goto LABEL_49;
      }
      if ( Counter == D3D10_COUNTER_GPU_IDLE )
      {
        v23 = "GPU Idle";
        v15 = 9;
        v24 = "A well-known counter to estimate the fractional amount of time for which the GPU was idle.";
LABEL_32:
        v25 = 91;
        goto LABEL_49;
      }
      v17 = Counter - 1;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( v18 )
        {
          v19 = v18 - 1;
          if ( v19 )
          {
            v20 = v19 - 1;
            if ( v20 )
            {
              v21 = v20 - 1;
              if ( v21 )
              {
                v22 = v21 - 1;
                if ( v22 )
                {
                  if ( v22 == 1 )
                  {
                    v23 = "Vertex Throughput Utilization";
                    v15 = 30;
                    v24 = "A well-known counter to estimate the fractional amount of vertex throughput utilized.";
                    v25 = 86;
                  }
                  else
                  {
                    v23 = "Triangle Setup Throughput Utilization";
                    v15 = 38;
                    v24 = "A well-known counter to estimate the fractional amount of triangle setup throughput utilized.";
                    v25 = 94;
                  }
                }
                else
                {
                  v23 = "Local Video Memory Bandwidth Utilization";
                  v15 = 41;
                  v24 = "A well-known counter to estimate the fractional amount of local video memory bandwidth utilized.";
                  v25 = 97;
                }
                goto LABEL_49;
              }
              v23 = "Host Adapter Bandwidth Utilization";
              v15 = 35;
              v24 = "A well-known counter to estimate the fractional amount of host adapter bandwidth utilized.";
              goto LABEL_32;
            }
            v23 = "Other GPU Processing";
            v15 = 21;
            v24 = "A well-known counter to estimate the fractional amount of time for which the GPU was workingon other p"
                  "rocessing, not directly related to vertex, geometry, or pixel processing.";
            v25 = 176;
          }
          else
          {
            v23 = "Pixel Processing";
            v15 = 17;
            v24 = "A well-known counter to estimate the fractional amount of time for which the GPU was workingon pixel processing.";
            v25 = 113;
          }
        }
        else
        {
          v23 = "Geometry Processing";
          v15 = 20;
          v24 = "A well-known counter to estimate the fractional amount of time for which the GPU was workingon geometry processing.";
          v25 = 116;
        }
LABEL_49:
        if ( pszDest )
          StringCchCopyA(pszDest, *a6, v23);
        if ( a7 )
          StringCchCopyA(a7, *a8, "fraction");
        if ( a9 )
          StringCchCopyA(a9, *a10, v24);
        if ( a6 )
          *a6 = v15;
        if ( a8 )
          *a8 = 9;
        if ( a10 )
          *a10 = v25;
        if ( a4 )
          *a4 = 0;
        *a3 = D3D11_COUNTER_TYPE_FLOAT32;
        return 0;
      }
      v23 = "Vertex Processing";
      v24 = "A well-known counter to estimate the fractional amount of time for which the GPU was workingon vertex processing.";
    }
    v25 = 114;
    goto LABEL_49;
  }
  catch ( _com_error *v32 )
  {
    if ( pszDest )
      *pszDest = 0;
    if ( a7 )
      *a7 = 0;
    if ( a9 )
      *a9 = 0;
    return *((unsigned int *)v32 + 2);
  }
  return result;
}

```

## disassembly

```asm
0x1800d3a80  push    rbx
0x1800d3a82  push    rsi
0x1800d3a83  push    rdi
0x1800d3a84  push    r12
0x1800d3a86  push    r14
0x1800d3a88  push    r15
0x1800d3a8a  sub     rsp, 68h
0x1800d3a8e  mov     r15, r9
0x1800d3a91  mov     r12, r8
0x1800d3a94  mov     rdi, rdx
0x1800d3a97  mov     rbx, rcx
0x1800d3a9a  test    rdx, rdx
0x1800d3a9d  jz      short loc_1800D3AAA
0x1800d3a9f  test    r8, r8
0x1800d3aa2  jz      short loc_1800D3AAA
0x1800d3aa4  cmp     dword ptr [rdx+4], 0
0x1800d3aa8  jz      short loc_1800D3AB4
0x1800d3aaa  mov     ecx, 80070057h; int
0x1800d3aaf  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800d3ab4  cmp     dword ptr [rdi], 0
0x1800d3ab7  jge     short loc_1800D3AC3
0x1800d3ab9  mov     eax, 80070057h
0x1800d3abe  jmp     loc_1800D3E38
0x1800d3ac3  cmp     dword ptr [rdi], 40000000h
0x1800d3ac9  jl      short loc_1800D3B33
0x1800d3acb  lea     rcx, [rbx-0F8h]; this
0x1800d3ad2  mov     rax, [rsp+98h+arg_48]
0x1800d3ada  mov     [rsp+98h+var_50], rax; unsigned int *
0x1800d3adf  mov     rax, [rsp+98h+arg_40]
0x1800d3ae7  mov     [rsp+98h+var_58], rax; char *
0x1800d3aec  mov     rax, [rsp+98h+arg_38]
0x1800d3af4  mov     [rsp+98h+var_60], rax; unsigned int *
0x1800d3af9  mov     rax, [rsp+98h+arg_30]
0x1800d3b01  mov     [rsp+98h+var_68], rax; char *
0x1800d3b06  mov     rax, [rsp+98h+arg_28]
0x1800d3b0e  mov     [rsp+98h+var_70], rax; unsigned int *
0x1800d3b13  mov     rax, [rsp+98h+pszDest]
0x1800d3b1b  mov     [rsp+98h+var_78], rax; char *
0x1800d3b20  mov     r9, r15; unsigned int *
0x1800d3b23  mov     r8, r12; enum D3D11_COUNTER_TYPE *
0x1800d3b26  mov     rdx, rdi; struct D3D11_COUNTER_DESC *
0x1800d3b29  call    ?CheckCounter@CDevice@@UEAAJPEBUD3D11_COUNTER_DESC@@PEAW4D3D11_COUNTER_TYPE@@PEAIPEAD23232@Z; CDevice::CheckCounter(D3D11_COUNTER_DESC const *,D3D11_COUNTER_TYPE *,uint *,char *,uint *,char *,uint *,char *,uint *)
0x1800d3b2e  jmp     loc_1800D3E38
0x1800d3b33  mov     ebx, 12h
0x1800d3b38  cmp     [rdi], ebx
0x1800d3b3a  jl      short loc_1800D3B46
0x1800d3b3c  mov     ecx, 80070057h; int
0x1800d3b41  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800d3b46  mov     ecx, [rdi]
0x1800d3b48  cmp     ecx, 9
0x1800d3b4b  jg      loc_1800D3CA3
0x1800d3b51  jz      loc_1800D3C87
0x1800d3b57  test    ecx, ecx
0x1800d3b59  jz      loc_1800D3C69
0x1800d3b5f  sub     ecx, 1
0x1800d3b62  jz      loc_1800D3C50
0x1800d3b68  sub     ecx, 1
0x1800d3b6b  jz      loc_1800D3C34
0x1800d3b71  sub     ecx, 1
0x1800d3b74  jz      loc_1800D3C18
0x1800d3b7a  sub     ecx, 1
0x1800d3b7d  jz      short loc_1800D3BFA
0x1800d3b7f  sub     ecx, 1
0x1800d3b82  jz      short loc_1800D3BE2
0x1800d3b84  sub     ecx, 1
0x1800d3b87  jz      short loc_1800D3BC6
0x1800d3b89  cmp     ecx, 1
0x1800d3b8c  jz      short loc_1800D3BAA
0x1800d3b8e  lea     r8, aTriangleSetupT; "Triangle Setup Throughput Utilization"
0x1800d3b95  mov     ebx, 26h ; '&'
0x1800d3b9a  lea     r11, aAWellKnownCoun; "A well-known counter to estimate the fr"...
0x1800d3ba1  lea     r10d, [rbx+38h]
0x1800d3ba5  jmp     loc_1800D3D9F
0x1800d3baa  lea     r8, aVertexThroughp; "Vertex Throughput Utilization"
0x1800d3bb1  mov     ebx, 1Eh
0x1800d3bb6  lea     r11, aAWellKnownCoun_0; "A well-known counter to estimate the fr"...
0x1800d3bbd  lea     r10d, [rbx+38h]
0x1800d3bc1  jmp     loc_1800D3D9F
0x1800d3bc6  lea     r8, aLocalVideoMemo; "Local Video Memory Bandwidth Utilizatio"...
0x1800d3bcd  mov     ebx, 29h ; ')'
0x1800d3bd2  lea     r11, aAWellKnownCoun_1; "A well-known counter to estimate the fr"...
0x1800d3bd9  lea     r10d, [rbx+38h]
0x1800d3bdd  jmp     loc_1800D3D9F
0x1800d3be2  lea     r8, aHostAdapterBan; "Host Adapter Bandwidth Utilization"
0x1800d3be9  mov     ebx, 23h ; '#'
0x1800d3bee  lea     r11, aAWellKnownCoun_2; "A well-known counter to estimate the fr"...
0x1800d3bf5  jmp     loc_1800D3C7C
0x1800d3bfa  lea     r8, aOtherGpuProces; "Other GPU Processing"
0x1800d3c01  mov     ebx, 15h
0x1800d3c06  lea     r11, aAWellKnownCoun_3; "A well-known counter to estimate the fr"...
0x1800d3c0d  mov     r10d, 0B0h
0x1800d3c13  jmp     loc_1800D3D9F
0x1800d3c18  lea     r8, aPixelProcessin; "Pixel Processing"
0x1800d3c1f  mov     ebx, 11h
0x1800d3c24  lea     r11, aAWellKnownCoun_4; "A well-known counter to estimate the fr"...
0x1800d3c2b  lea     r10d, [rbx+60h]
0x1800d3c2f  jmp     loc_1800D3D9F
0x1800d3c34  lea     r8, aGeometryProces; "Geometry Processing"
0x1800d3c3b  mov     ebx, 14h
0x1800d3c40  lea     r11, aAWellKnownCoun_5; "A well-known counter to estimate the fr"...
0x1800d3c47  lea     r10d, [rbx+60h]
0x1800d3c4b  jmp     loc_1800D3D9F
0x1800d3c50  lea     r8, aVertexProcessi; "Vertex Processing"
0x1800d3c57  lea     r11, aAWellKnownCoun_6; "A well-known counter to estimate the fr"...
0x1800d3c5e  mov     r10d, 72h ; 'r'
0x1800d3c64  jmp     loc_1800D3D9F
0x1800d3c69  lea     r8, aGpuIdle; "GPU Idle"
0x1800d3c70  mov     ebx, 9
0x1800d3c75  lea     r11, aAWellKnownCoun_7; "A well-known counter to estimate the fr"...
0x1800d3c7c  mov     r10d, 5Bh ; '['
0x1800d3c82  jmp     loc_1800D3D9F
0x1800d3c87  lea     r8, aFillRateUtiliz; "Fill Rate Utilization"
0x1800d3c8e  mov     ebx, 16h
0x1800d3c93  lea     r11, aAWellKnownCoun_8; "A well-known counter to estimate the fr"...
0x1800d3c9a  lea     r10d, [rbx+43h]
0x1800d3c9e  jmp     loc_1800D3D9F
0x1800d3ca3  sub     ecx, 0Ah
0x1800d3ca6  jz      loc_1800D3D88
0x1800d3cac  sub     ecx, 1
0x1800d3caf  jz      loc_1800D3D6F
0x1800d3cb5  sub     ecx, 1
0x1800d3cb8  jz      loc_1800D3D57
0x1800d3cbe  sub     ecx, 1
0x1800d3cc1  jz      short loc_1800D3D3E
0x1800d3cc3  sub     ecx, 1
0x1800d3cc6  jz      short loc_1800D3D25
0x1800d3cc8  sub     ecx, 1
0x1800d3ccb  jz      short loc_1800D3D0C
0x1800d3ccd  cmp     ecx, 1
0x1800d3cd0  jz      short loc_1800D3CF0
0x1800d3cd2  lea     r8, aTextureCacheHi; "Texture Cache Hit Rate"
0x1800d3cd9  mov     ebx, 17h
0x1800d3cde  lea     r11, aAWellKnownCoun_9; "A well-known counter to estimate the fr"...
0x1800d3ce5  mov     r10d, 9Fh
0x1800d3ceb  jmp     loc_1800D3D9F
0x1800d3cf0  lea     r8, aPostVertexShad; "Post Vertex-Shader Vertex Cache Hit Rat"...
0x1800d3cf7  mov     ebx, 29h ; ')'
0x1800d3cfc  lea     r11, aAWellKnownCoun_10; "A well-known counter to estimate the fr"...
0x1800d3d03  lea     r10d, [rbx+7Fh]
0x1800d3d07  jmp     loc_1800D3D9F
0x1800d3d0c  lea     r8, aPixelShaderCom; "Pixel Shader Computation Limited"
0x1800d3d13  mov     ebx, 21h ; '!'
0x1800d3d18  lea     r11, aAWellKnownCoun_11; "A well-known counter to estimate the fr"...
0x1800d3d1f  lea     r10d, [rbx+4Ah]
0x1800d3d23  jmp     short loc_1800D3D9F
0x1800d3d25  lea     r8, aPixelShaderMem; "Pixel Shader Memory Limited"
0x1800d3d2c  mov     ebx, 1Ch
0x1800d3d31  lea     r11, aAWellKnownCoun_12; "A well-known counter to estimate the fr"...
0x1800d3d38  lea     r10d, [rbx+53h]
0x1800d3d3c  jmp     short loc_1800D3D9F
0x1800d3d3e  lea     r8, aGeometryShader; "Geometry Shader Computation Limited"
0x1800d3d45  mov     ebx, 24h ; '$'
0x1800d3d4a  lea     r11, aAWellKnownCoun_13; "A well-known counter to estimate the fr"...
0x1800d3d51  lea     r10d, [rbx+4Ah]
0x1800d3d55  jmp     short loc_1800D3D9F
0x1800d3d57  lea     r8, aGeometryShader_0; "Geometry Shader Memory Limited"
0x1800d3d5e  mov     ebx, 1Fh
0x1800d3d63  lea     r11, aAWellKnownCoun_14; "A well-known counter to estimate the fr"...
0x1800d3d6a  jmp     loc_1800D3C5E
0x1800d3d6f  lea     r8, aVertexShaderCo; "Vertex Shader Computation Limited"
0x1800d3d76  mov     ebx, 22h ; '"'
0x1800d3d7b  lea     r11, aAWellKnownCoun_15; "A well-known counter to estimate the fr"...
0x1800d3d82  lea     r10d, [rbx+4Ah]
0x1800d3d86  jmp     short loc_1800D3D9F
0x1800d3d88  lea     r8, aVertexShaderMe; "Vertex Shader Memory Limited"
0x1800d3d8f  mov     ebx, 1Dh
0x1800d3d94  lea     r11, aAWellKnownCoun_16; "A well-known counter to estimate the fr"...
0x1800d3d9b  lea     r10d, [rbx+53h]
0x1800d3d9f  mov     rcx, [rsp+98h+pszDest]; pszDest
0x1800d3da7  mov     r14, [rsp+98h+arg_28]
0x1800d3daf  test    rcx, rcx
0x1800d3db2  jz      short loc_1800D3DBC
0x1800d3db4  mov     edx, [r14]; cchDest
0x1800d3db7  call    StringCchCopyA
0x1800d3dbc  mov     rcx, [rsp+98h+arg_30]; pszDest
0x1800d3dc4  mov     rsi, [rsp+98h+arg_38]
0x1800d3dcc  test    rcx, rcx
0x1800d3dcf  jz      short loc_1800D3DDF
0x1800d3dd1  mov     edx, [rsi]; cchDest
0x1800d3dd3  lea     r8, aFraction; "fraction"
0x1800d3dda  call    StringCchCopyA
0x1800d3ddf  mov     rcx, [rsp+98h+arg_40]; pszDest
0x1800d3de7  mov     rdi, [rsp+98h+arg_48]
0x1800d3def  test    rcx, rcx
0x1800d3df2  jz      short loc_1800D3DFE
0x1800d3df4  mov     edx, [rdi]; cchDest
0x1800d3df6  mov     r8, r11; pszSrc
0x1800d3df9  call    StringCchCopyA
0x1800d3dfe  test    r14, r14
0x1800d3e01  jz      short loc_1800D3E06
0x1800d3e03  mov     [r14], ebx
0x1800d3e06  test    rsi, rsi
0x1800d3e09  jz      short loc_1800D3E11
0x1800d3e0b  mov     dword ptr [rsi], 9
0x1800d3e11  test    rdi, rdi
0x1800d3e14  jz      short loc_1800D3E19
0x1800d3e16  mov     [rdi], r10d
0x1800d3e19  test    r15, r15
0x1800d3e1c  jz      short loc_1800D3E25
0x1800d3e1e  mov     dword ptr [r15], 0
0x1800d3e25  mov     dword ptr [r12], 0
0x1800d3e2d  xor     eax, eax
0x1800d3e2f  jmp     short loc_1800D3E38
0x1800d3e31  mov     eax, [rsp+98h+arg_0]
0x1800d3e38  add     rsp, 68h
0x1800d3e3c  pop     r15
0x1800d3e3e  pop     r14
0x1800d3e40  pop     r12
0x1800d3e42  pop     rdi
0x1800d3e43  pop     rsi
0x1800d3e44  pop     rbx
0x1800d3e45  retn
```
